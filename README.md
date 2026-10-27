# ITI Voyager Reader

A lightweight browser-based PDF reader. The stable reader lives in `index.html`.

## Experimental Piper integration

- `voice-lab.html`: voice selection notes and links.
- `piper-engine.js`: browser Piper engine adapted for this experiment.
- `piper-reader-test.html`: isolated PDF-to-Piper synthesis test.

Selected model: `en_US-libritts_r-medium`; sample label: `lilbritts_r`; source speaker ID `3922` maps to model speaker index `0` in the published model metadata. Model file is approximately 78.6 MB, plus its JSON configuration and browser runtime.

The model and config are loaded from the upstream Piper voice repository. ONNX Runtime Web and phonemizer are loaded through browser module CDNs. The browser caches the model where supported. The first run requires internet access; this is not yet a fully bundled offline install.

## Test steps

1. Serve the branch over HTTPS or localhost (ES modules, PDF.js, model fetches, and WASM do not work reliably from `file://`).
2. Open `piper-reader-test.html`.
3. Load Piper and wait for the model to finish loading.
4. Choose a text-based PDF and extract its text, or use the sample text.
5. Generate and play the narration; note any browser console or network errors.

## Status and safety

The browser demo was manually confirmed to generate speech. The new in-repository PDF-to-Piper page has been committed to the isolated branch but has **not yet been executed end to end in a browser**. It is an experimental integration test, not a production-ready reader change. The stable `index.html` matches `main` exactly. Do not merge until browser testing confirms model loading, phonemization, audio output, PDF extraction, and acceptable licensing/redistribution terms.

No paid speech API is used by this experiment.
