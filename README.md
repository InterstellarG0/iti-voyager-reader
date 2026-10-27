 ITI Voyager Reader - starter prototype

A phone-friendly PDF text-to-speech reader prototype by Interstellar Technologies Initiative.

 Current features
- Choose a PDF from the device
- Extract selectable text in the browser with PDF.js
- Play, pause, stop, move backward/forward by section
- Choose from browser/device voices and adjust speech speed
- Save a basic reading position in browser local storage
- Responsive dark interface with large controls

Important limitations
- **This is a prototype, not a finished offline package.** PDF.js and its worker are loaded from a CDN in this starter. First-time PDF import therefore needs an internet connection.
- For a truly offline release, include PDF.js files in the repository and configure a service worker/PWA or serve the files from a local secure origin.
- Browser speech voices vary by device. For natural neural offline narration, users can install a compatible Android text-to-speech engine/voice. A future native Android wrapper could integrate a local neural engine more reliably.
- Scanned PDFs need OCR; this prototype only extracts selectable text.
- Speech pause/resume and voice behavior differ across browsers.
- This prototype does not upload PDFs. The document is read in the browser; bookmark position is stored locally by filename.

Quick test
1. Open `index.html` in a browser while connected to the internet.
2. Select a text-based PDF.
3. Choose an available voice and press Play.
4. Test pause, stop, section navigation, speed, and Save place.

Suggested next iteration
1. Bundle PDF.js locally and verify its license/notices.
2. Add robust page/paragraph navigation and a saved library.
3. Add OCR as an optional offline module.
4. Benchmark offline neural TTS options on target Android hardware.
5. Add a PWA service worker and test airplane-mode behavior.
6. Add a proper repository license after deciding how ITI wants to license the app and dependencies.

Repository structure
- `index.html` — prototype UI and logic
- `manifest.webmanifest` — installable web-app metadata
- `README.md` — setup and limitations

License
No project license has been selected yet. Do not assume the code is open-source licensed until ITI adds a license file.
