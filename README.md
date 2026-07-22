# Object-Scanner


An edge-AI, 100% browser-native computer vision application that turns any webcam into an interactive visual assistant. 

Everything runs directly inside your web browser using client-side machine learning models—**zero server processing, zero API costs, and total data privacy.**

![License](https://img.shields.io/badge/license-MIT-green.svg)
![JavaScript](https://img.shields.io/badge/javascript-ES6%2B-yellow.svg)
![TensorFlow.js](https://img.shields.io/badge/TensorFlow.js-4.10.0-orange.svg)
![Privacy](https://img.shields.io/badge/Privacy-100%25%20On--Device-blue.svg)

---

## 🌟 Key Features

* 🧠 **Real-Time Object Detection & Memory**
  * Powered by `TensorFlow.js` and `COCO-SSD` (MobileNet v2).
  * Detects everyday objects and people live on camera.
  * **Custom Memory & Corrections:** Correct wrong AI predictions (e.g., re-labeling "cup" to "My Thermos"). Corrections are saved across sessions using `localStorage`.

* 🖐️ **Hand Gesture Recognition**
  * Powered by Google's `MediaPipe Tasks Vision`.
  * Detects hand joints and recognizes real-time gestures (thumbs up/down, victory, fist, open palm, pointing, and "I love you" signs) with confidence scoring.

* 😀 **Facial Expression & Emotion Tracking**
  * Powered by `face-api.js`.
  * Tracks human faces and analyzes emotional expressions in real time (happy, neutral, surprised, sad, angry, fearful, disgusted).

* 📄 **Physical Text Reader (OCR)**
  * Powered by `Tesseract.js`.
  * Captures live frame snapshots, performs contrast/grayscale preprocessing for enhanced clarity, and extracts physical text into editable text.

* 🏁 **QR & Barcode Scanning**
  * Powered by browser-native `BarcodeDetector` with a `jsQR` engine fallback.
  * Scans QR codes, UPCs, EAN-13, and Code 128 barcodes.
  * Automatically converts detected web URLs into clickable open-link buttons.

* 🔊 **Accessibility & Speech Synthesis**
  * Uses the browser-native `Web Speech API` to read decoded QR codes and OCR text aloud automatically or on demand.

---

## 🛠️ Tech Stack & Dependencies

All dependencies are loaded on-demand via high-performance CDNs:

* **Object Detection:** `@tensorflow/tfjs` & `@tensorflow-models/coco-ssd`
* **Hand Landmarks & Gestures:** `@mediapipe/tasks-vision`
* **Face & Emotion Analysis:** `face-api.js`
* **Optical Character Recognition (OCR):** `tesseract.js`
* **QR Reader:** `jsQR`
* **Styling & Engine:** Vanilla HTML5, CSS3, JavaScript (ES Modules)

---

## 🚀 Quick Start / Local Setup

Because Object Scanner is built entirely with client-side code, **no build step, Node.js installation, or backend server is required.**

### Method 1: Direct File Launch
1. Clone or download this repository:
   ```bash
   git clone [https://github.com/YOUR_USERNAME/object-scanner.git](https://github.com/YOUR_USERNAME/object-scanner.git)
