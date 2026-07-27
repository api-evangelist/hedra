---
name: Generate an image with Hedra
description: Submit a text-to-image generation to the Hedra Web API and retrieve the finished image.
api: openapi/hedra-web-api-openapi-original.json
operations:
  - list_models_public_models_get
  - generate_asset_public_generations_post
  - get_status_public_generations__generation_id__status_get
---

# Generate an image with Hedra

Base URL: `https://api.hedra.com/web-app`
Auth: send header `X-API-Key: <key>` on every request. A paid account with API credits is required (manage keys at https://www.hedra.com/develop/api-keys).

## Steps

1. **(Optional) Pick a model** — `GET /public/models` (`list_models_public_models_get`). Filter for image models and note the `slug`. Pass it as `model_slug` (the UUID `ai_model_id` is deprecated).

2. **Submit the generation** — `POST /public/generations` (`generate_asset_public_generations_post`). The body is discriminated by `type`; use `type: "image"` (a `GenerateImageRequest`):
   ```json
   { "type": "image", "text_prompt": "a neon koi fish", "model_slug": "<slug>", "aspect_ratio": "16:9", "batch_size": 1 }
   ```
   `text_prompt` is required. Response returns a `Generation` with an `id` and `status` of `queued`/`processing`.

3. **Poll for completion** — `GET /public/generations/{generation_id}/status` (`get_status_public_generations__generation_id__status_get`). Repeat with backoff until `status` is `complete` (then read `url` / `download_url`) or `error`. Use `progress` (0–1) and `eta_sec` to pace polling. Webhooks are an alternative to polling (see conventions).

## Rules

- **Errors** carry an `ErrorCode` on `error.type` / `error_message` (see `errors/hedra-error-codes.yml`). `MISSING_CREDITS` → buy credits; `MODERATION_FAILED` → revise the prompt; `RESOURCE_EXHAUSTED` → back off. Request validation failures return HTTP 422.
- **Idempotency**: no `Idempotency-Key` header exists; to de-duplicate, pre-reserve `generation_id`/`reserved_asset_id` rather than resubmitting blindly.
- **Batching**: `batch_size` 1–8; results share a `batch_generation_id`.
- Check the balance any time with `GET /public/billing/credits`.
