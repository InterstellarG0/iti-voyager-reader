# ITI Voyager — Piper Voice Lab

This is an isolated evaluation page. It does not modify or replace Voyager Reader's working `index.html` and does not pretend that Piper is already integrated.

## Selected voice (2026-10-27)
- Model: `en_US-libritts_r-medium`
- Sample-browser label: `lilbritts_r`
- Speaker ID shown by the user: `3922`
- Reference: https://rhasspy.github.io/piper-samples/#en_US-libritts_r-medium

The voice is selected as the baseline, but the sample label-to-speaker-ID mapping must be verified against model metadata before claiming it is wired into the reader. This lab currently links to the sample catalog; it does not yet synthesize speech with this model inside the page.

## Quick test
1. Open `index.html` through GitHub Pages or a local HTTP server (not `file://` if browser restrictions interfere).
2. Click **Open Piper browser demo**.
3. Copy the same audition paragraph and paste it into the demo.
4. Listen for American English pronunciation, cadence, clarity, and long-session comfort.

The linked upstream browser demo is a separate experiment and may not bundle the selected LibriTTS-R speaker. Use the sample catalog link to confirm the target voice; actual integration still requires a compatible browser runtime plus the model and matching JSON configuration. The page calls out Lessac as a candidate requiring its ONNX model and matching JSON config to be added. Spanish needs a separate voice model. Voice files may be tens of megabytes and each voice's license must be reviewed before redistribution/commercial deployment.

## Upstream references
- https://github.com/piper-tts/piper-tts.github.io
- https://tderflinger.github.io/piper-docs/about/voices/

## Important
This is a test harness and listening workflow, not a finished Piper integration. No paid API, token, or hosted speech request is used by this page itself.
