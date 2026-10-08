# Object-Scanner

An edge-AI, 100% browser-native computer vision app that turns any webcam into an interactive visual assistant.

Everything runs inside your web browser using client-side machine learning models: **no server processing, no API costs, and your camera feed never leaves your device.**

![License](https://img.shields.io/badge/license-MIT-green.svg)
![JavaScript](https://img.shields.io/badge/javascript-ES6%2B-yellow.svg)
![TensorFlow.js](https://img.shields.io/badge/TensorFlow.js-4.10.0-orange.svg)
![Privacy](https://img.shields.io/badge/Privacy-100%25%20On--Device-blue.svg)

---

## Key Features

* **Real-time object detection and memory**
  * Powered by `TensorFlow.js` and `COCO-SSD` (MobileNet v2).
  * Detects everyday objects and people live on camera, with a live item counter.
  * **Custom corrections:** fix a wrong prediction (for example, re-label "cup" as "My Thermos"). Corrections and confirmations are saved across sessions in `localStorage`.

* **Hand gesture recognition**
  * Powered by Google's `MediaPipe Tasks Vision`.
  * Draws the hand skeleton and recognizes thumbs up/down, victory, fist, open palm, pointing and "I love you", with confidence scores.
  * **Pointer / Draw mode:** use your index finger as a pen to draw on the video. Use *Clear Drawings* to wipe the canvas.

* **Facial expression tracking**
  * Powered by `face-api.js`.
  * Tracks faces and reads expressions in real time (happy, neutral, surprised, sad, angry, fearful, disgusted).

* **Text reader (OCR)**
  * Powered by `Tesseract.js`.
  * Captures the current frame, applies grayscale and contrast preprocessing, and extracts the text.

* **QR and barcode scanning**
  * Uses the browser-native `BarcodeDetector` with a `jsQR` fallback.
  * Reads QR codes, UPC, EAN-13 and Code 128. Detected web links become clickable.

* **Target color finder**
  * Samples the pixel at the center crosshair and names the closest color, with its hex and RGB values.

* **Cyberpunk HUD and visual filters**
  * Optional HUD overlay with a scanline and a live FPS readout.
  * Filters: Cyberpunk Neon, Thermal Vision and Matrix Green. Zoom slider included.

* **Session log and export**
  * Scanned codes, OCR reads and saved objects are logged. Export the log as CSV or JSON.

* **Accessibility**
  * Uses the Web Speech API to read QR codes and OCR text aloud, automatically or on demand.

---

## Tech Stack

All dependencies load from CDNs, so there is nothing to install:

| Purpose | Library |
|---------|---------|
| Object detection | `@tensorflow/tfjs`, `@tensorflow-models/coco-ssd` |
| Hand landmarks and gestures | `@mediapipe/tasks-vision` |
| Face and emotion analysis | `face-api.js` |
| OCR | `tesseract.js` |
| QR fallback reader | `jsQR` |
| UI | Vanilla HTML, CSS and JavaScript (ES modules) |

---

## Quick Start

There is no build step and no backend. The app is a single `index.html` file.

> **Camera access requires a secure context.** Browsers only allow webcam access on `https://` pages or on `http://localhost`. Opening the file directly or serving it over plain `http://` on another address may block the camera, so use one of the options below.

### Option 1: Run it locally

```bash
git clone https://github.com/AlviSarwar/Object-Scanner.git
cd Object-Scanner

# pick any static server, for example:
python3 -m http.server 8000
```

Then open <http://localhost:8000> in a modern browser.

### Option 2: Host it for free on GitHub Pages

1. Go to **Settings -> Pages** in your repository.
2. Under **Build and deployment**, choose **Deploy from a branch**, then select `main` and `/ (root)`.
3. Open the URL GitHub gives you. Pages serves over HTTPS, so the camera works.

---

## How to Use

1. Wait for the status to read **Model ready**, then click **Start Camera** and allow access.
2. Detected objects appear live. Use the check button to confirm a label or the pencil to rename it.
3. Switch on any extra module with the toggles (hand gestures, pointer/draw, face reactions, QR/barcodes, HUD, read aloud).
4. Press **Read Text On Screen** to run OCR on the current frame.

The first time you enable hand gestures, face reactions or OCR, the matching model is downloaded, so the first use takes a moment.

---

## Browser Support

Works in current Chrome, Edge and Safari. Firefox works too, but it lacks the native `BarcodeDetector`, so QR scanning falls back to `jsQR` and other barcode formats may not be read. A device with a webcam and a reasonably modern GPU gives the smoothest frame rate.

---

## Privacy

Detection, recognition and OCR all run on your device. The CDN scripts and model files are downloaded when needed, but your video frames are never uploaded. Corrections you save stay in your browser's `localStorage`.

---

## License

Released under the [MIT License](LICENSE).
