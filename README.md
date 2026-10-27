# ITI Voyager Reader

**Listen to text-based PDFs in your browser.** ITI Voyager Reader is a lightweight, mobile-friendly reader from Interstellar Technologies Initiative. It extracts PDF text locally in the browser, offers browser-provided voices, and includes an experimental Piper neural voice option.

**Try it:** https://interstellarg0.github.io/iti-voyager-reader/

## Current features

- Load a text-based PDF from your device; the PDF itself is not uploaded by this app.
- Read aloud with voices available from your browser or device.
- Optional **Piper Voice Lab** neural narration using the `en_US-libritts_r-medium` voice model.
- Adjust reading speed, pause, resume, stop, and move backward or forward through reading sections.
- See extracted text and track reading progress.
- Use **Save place** to bookmark your current section and restore it after reloading the page, for the same PDF filename in the same browser.
- Text cleanup and sentence/paragraph chunking to improve pronunciation and pacing.
- Mobile-friendly default browser voice selection and smaller Piper inference requests on mobile.

## Using the reader

1. Open the [live reader](https://interstellarg0.github.io/iti-voyager-reader/).
2. Choose a text-based PDF.
3. Select a browser voice, or choose **Piper Voice Lab — experimental**.
4. Set your reading speed and press **Play**.
5. Press **Save place** whenever you want to bookmark your current section.

### Important notes

- **Save place is manual.** Press Save place before closing or reloading if you want to bookmark the current section. The bookmark is stored in browser local storage and keyed by the PDF filename; clearing site data or using another browser/device will not carry it over.
- **Piper is experimental.** Its first use downloads approximately 79 MB of model data, plus runtime dependencies. It needs a modern browser with WebAssembly support and an internet connection for initial downloads.
- **Text-based PDFs only.** Scanned PDFs without selectable text require OCR, which is not included yet.
- **Internet is currently required to load PDF.js and the initial Piper dependencies/model.** This is not yet a fully bundled offline installation.
- Browser voices differ by device and operating system. Voice availability, background playback, and performance depend on the browser/device.

## Development and testing

The app is a static browser project. The main files are:

- `index.html` — reader interface, PDF extraction, browser speech, text cleanup, progress, and saved place.
- `piper-engine.js` — experimental Piper inference engine.
- `manifest.webmanifest` — web app metadata.

For local testing, serve the project from localhost or HTTPS rather than opening the HTML with `file://`. Load a text-based PDF, test browser narration and navigation, then test Piper model loading, audio playback, pause/resume, and saved-place behavior.

The current code has been committed to the default branch and the live GitHub Pages URL is available above. The code has been checked in the repository, but Piper audio has not yet been independently verified end-to-end across browsers and mobile devices. A previously reported Piper inference error on some document text may still need further testing.

## Privacy

The selected PDF is processed in the browser and is not uploaded by the reader. External resources are loaded for PDF.js and, when selected, Piper's model/runtime. The app uses local browser storage only for the saved reading position.
