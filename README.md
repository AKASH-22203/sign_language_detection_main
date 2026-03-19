# Sign Language Detection System 🚀

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-2.0%2B-brightgreen)](https://flask.palletsprojects.com/)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.5%2B-red)](https://opencv.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📖 Overview

A real-time **Sign Language Detection** application using computer vision and deep learning. Detects hand gestures from images, videos, or webcam feed and classifies them into sign language alphabets/words using a pre-trained Keras model.

**Key Features:**

- 🖼️ **Image Upload Detection** via web interface
- 🎥 **Video Upload Detection** (samples frames for efficiency)
- 📹 **Live Webcam Detection** (real-time)
- 🖱️ **Data Collection Tool** for custom gesture training
- ⚡ **Fast Inference** with cvzone HandTracking & Classification modules
- 🌐 **Flask Web App** with clean UI

## 🛠️ Tech Stack

- **Backend**: Flask, OpenCV, NumPy
- **Computer Vision**: cvzone (HandTrackingModule, ClassificationModule)
- **ML Model**: Keras/TensorFlow (.h5 model + labels)
- **Frontend**: HTML/CSS (templates/static)

## 🚀 Quick Start

### 1. Clone/Setup

```bash
# Unzip or navigate to project
cd Sign_Language_Detection-main
```

### 2. Install Dependencies

```bash
pip install flask opencv-python cvzone tensorflow keras numpy
```

### 3. Run Web Application

```bash
python app.py
```

- Open `http://127.0.0.1:5000/` in browser
- Upload image/video or click "Test Webcam"

### 4. Test Webcam (Standalone)

```bash
python test.py
```

- Shows live detection with bounding box & label

### 5. Collect Data for Custom Training

```bash
python datacollection.py
```

- Press `S` to save cropped hand images to `Sign-Language-detection/Hii/`

## 📁 Project Structure

```
Sign_Language_Detection-main/
├── app.py              # Flask web app
├── test.py             # Webcam real-time detection
├── datacollection.py   # Data collection script
├── main.py             # TensorFlow/Keras version check
├── Model/
│   ├── keras_model.h5  # Pre-trained classifier
│   └── labels.txt      # Gesture labels (e.g., A, B, C...)
├── templates/
│   └── index.html      # Web UI
├── static/
│   └── style.css       # Styles
├── uploads/            # Temp uploads (auto-cleaned)
└── TODO.md             # Pending tasks
```

## 🔍 How It Works

1. **Hand Detection**: cvzone HandDetector finds hand bbox
2. **Preprocessing**: Crop, resize to 300x300 white canvas (preserves aspect ratio)
3. **Classification**: Keras model predicts gesture from `labels.txt`
4. **Output**: Displays label (e.g., "A", "Hello")

**Supported Gestures**: Defined in `Model/labels.txt` (26 English alphabets typically).

## 📱 Web App Usage

1. Start `app.py`
2. **Upload Image**: Select file → Get instant prediction
3. **Upload Video**: Processes sampled frames → Unique detections
4. **Test Webcam**: Runs `test.py` in background


## ⚙️ Model Training (Optional)

1. Collect data: `datacollection.py`
2. Use [cvzone training example](https://github.com/CvZone/CvZone) to retrain `keras_model.h5`
3. Update `labels.txt`

## 🔧 Troubleshooting

- **No module 'cvzone'**: `pip install cvzone`
- **Model not found**: Ensure `Model/keras_model.h5` & `labels.txt` exist
- **Webcam issues**: Check camera permissions, try `python test.py`
- **CUDA errors**: Install TensorFlow CPU version

**Dependencies Issues?**

```bash
pip install --upgrade tensorflow opencv-python cvzone flask numpy
```


## 🤝 Contributing

1. Improve UI in `templates/index.html`
2. Add new gestures via data collection

---

**Built with ❤️ for accessibility** | ⭐ Star if helpful!
