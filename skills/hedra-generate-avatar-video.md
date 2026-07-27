---
name: Generate an avatar video with Hedra
description: Upload a portrait and a voice track, then generate a Character-3 talking-head video with the Hedra Web API.
api: openapi/hedra-web-api-openapi-original.json
operations:
  - create_asset_public_assets_post
  - upload_asset_public_assets__id__upload_post
  - generate_asset_public_generations_post
  - get_status_public_generations__generation_id__status_get
---

# Generate an avatar video with Hedra

Base URL: `https://api.hedra.com/web-app`. Auth: `X-API-Key` header on every request.

Hedra's marquee flow is a talking-head / character video driven by an image plus audio (Character-3 / Avatar / Omnia models). Assets must be uploaded first, then referenced by id in the generation.

## Steps

1. **Reserve the image asset** — `POST /public/assets` (`create_asset_public_assets_post`) with `{ "name": "portrait", "type": "image" }`. Save the returned `id`.
2. **Upload the image bytes** — `POST /public/assets/{id}/upload` (`upload_asset_public_assets__id__upload_post`), `multipart/form-data`, using the id from step 1.
3. **Reserve + upload the audio** — repeat steps 1–2 with `type: "audio"` to get an `audio_asset_id`. (Or generate audio first with the text-to-speech skill and reuse that asset.)
4. **Submit the avatar video** — `POST /public/generations` (`generate_asset_public_generations_post`) with:
   ```json
   { "type": "video", "model_slug": "<avatar-model-slug>", "start_keyframe_id": "<image_asset_id>", "audio_id": "<audio_asset_id>" }
   ```
   Save the returned generation `id`.
5. **Poll** — `GET /public/generations/{generation_id}/status` until `status` is `complete` (read `url`/`download_url`/`streaming_url`) or `error`.

## Rules

- Choose an avatar-capable model via `GET /public/models`; models advertise `requires_audio_input` / `requires_start_frame`.
- Same error/idempotency/credit rules as the image skill (`errors/hedra-error-codes.yml`, `conventions/hedra-conventions.yml`).
- Video generations may be batched (`batch_size` 1–8) and can specify `end_keyframe_id`, `audio_start_ms`, and reference assets.
