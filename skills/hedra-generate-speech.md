---
name: Generate text-to-speech with Hedra
description: Convert text to speech using a Hedra built-in or cloned voice and retrieve the audio.
api: openapi/hedra-web-api-openapi-original.json
operations:
  - list_voices_public_voices_get
  - generate_asset_public_generations_post
  - get_status_public_generations__generation_id__status_get
  - get_credits_public_billing_credits_get
---

# Generate text-to-speech with Hedra

Base URL: `https://api.hedra.com/web-app`. Auth: `X-API-Key` header on every request.

## Steps

1. **Pick a voice** — `GET /public/voices` (`list_voices_public_voices_get`). Each `Voice` has an `external_id`, `labels`, and a `preview_url`. Save the id you want.
2. **(Optional) Check credits** — `GET /public/billing/credits` (`get_credits_public_billing_credits_get`). Audio bills ~15 credits per 1,000 characters.
3. **Submit the TTS generation** — `POST /public/generations` (`generate_asset_public_generations_post`) with a `GenerateTextToSpeechRequest`:
   ```json
   { "type": "text_to_speech", "voice_id": "<external_id>", "text": "Hello from Hedra", "model_slug": "<slug>", "stability": 0.5, "speed": 1.0, "language": "en" }
   ```
   `voice_id` and `text` are required. `stability` 0–1, `speed` 0.7–1.2. Save the generation `id`.
4. **Poll** — `GET /public/generations/{generation_id}/status` until `status` is `complete` (read `url`/`download_url`) or `error`.

## Rules

- Errors surface via `error.type` (`ErrorCode`) / `error_message`; validation errors return HTTP 422. See `errors/hedra-error-codes.yml`.
- No `Idempotency-Key`; pre-reserve `generation_id` to de-duplicate. See `conventions/hedra-conventions.yml`.
- For voice cloning, use `type: "voice_clone"` (`GenerateVoiceCloneRequest`) with a reference audio asset; the resulting voice can then drive TTS or avatar video.
