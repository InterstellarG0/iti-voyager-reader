# ITI Voyager Reader

A lightweight browser-based PDF reader. The stable reader lives in `index.html`.

## Piper voice experiment

Open `voice-lab.html` to audition the selected voice and copy a consistent narration passage. The page links to the browser Piper demo that was tested during development.

- Selected model candidate: `en_US-libritts_r-medium`
- Sample label: `lilbritts_r`
- Candidate speaker ID: `3922` (verify against the model metadata before shipping)
- Browser demo: https://clowerweb.github.io/piper-tts-web-demo/
- Upstream sample catalog: https://rhasspy.github.io/piper-samples/#en_US-libritts_r-medium

## Current status

The browser demo generated speech successfully in a manual test. This does **not** mean Piper has been integrated into the reader. The reader currently retains its existing browser speech-synthesis behavior. No paid speech API is used by this experiment.

## Safe workflow

Keep voice work on the `iti-piper-voice-lab` branch until the model/config pairing, browser runtime, licensing, PDF text handoff, and pause/resume/stop behavior have been tested end to end. Do not merge into `main` until the integration is verified.
