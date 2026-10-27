# ITI Voyager Reader

A lightweight browser-based PDF reader. The `main` branch is the stable baseline; `iti-piper-voice-lab` contains experimental Piper integration in the reader dropdown.

## Experimental Piper integration

- `voice-lab.html`: voice selection notes and links.
- `piper-engine.js`: browser Piper engine adapted for this experiment.
- `piper-reader-test.html`: isolated PDF-to-Piper synthesis test.
- On this lab branch only, the main reader dropdown includes `Piper — lilbritts_r`; browser voices remain available.

Selected model: `en_US-libritts_r-medium`; sample label: `lilbritts_r`; source speaker ID `3922` maps to model speaker index `0` in the published model metadata. Model file is approximately 78.6 MB, plus its JSON configuration and browser runtime.

The model and config are loaded from the upstream Piper voice repository. ONNX Runtime Web and phonemizer are loaded through browser module CDNs. The browser caches the model where supported. The first run requires internet access; this is not yet a fully bundled offline install.

## Test steps

1. Serve the branch over HTTPS or localhost (ES modules, PDF.js, model fetches, and WASM do not work reliably from `file://`).
2. Open `piper-reader-test.html`.
3. Load Piper and wait for the model to finish loading.
4. Choose a text-based PDF and extract its text, or use the sample text.
5. Generate and play the narration; note any browser console or network errors.

## Status and safety

The upstream Piper demo was manually confirmed to generate speech, but this repository's implementation—including the new dropdown path—has **not yet been executed end to end in a browser**. The lab branch adds Piper loading, synthesis, audio playback, pause/resume, stop, and section navigation hooks. Treat it as experimental. Do not merge until browser testing confirms model loading, phonemization, audio output, PDF extraction, playback controls, and acceptable licensing/redistribution terms. The `main` branch has not been changed.

No paid speech API is used by this experiment.
