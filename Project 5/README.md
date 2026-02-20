<div align="center">

# 😶‍🌫️ Real-Time Emotion Detection System

[![Portfolio](https://img.shields.io/badge/🌐_Portfolio-Live-7C4DFF?style=for-the-badge)](https://programmer-akash.github.io/portfolio/)
[![GitHub](https://img.shields.io/badge/GitHub-programmer--akash-181717?style=for-the-badge&logo=github)](https://github.com/programmer-akash)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-coder--akash--halder-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/coder-akash-halder/)
[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-4.x-5C3EE8?style=for-the-badge&logo=opencv)](https://opencv.org/)
[![Keras](https://img.shields.io/badge/Keras-Deep_Learning-D00000?style=for-the-badge&logo=keras)](https://keras.io/)

*Detects human emotions in real-time using webcam feed — built without DeepFace*

</div>

---

## 📌 Overview

This project is a **Real-Time Emotion Detection System** that uses a webcam feed to detect faces and classify emotions — all in real time. It uses **OpenCV** for face detection and a custom **Keras deep learning model** for emotion classification, without relying on any heavy third-party libraries like DeepFace.

The system can recognize **7 human emotions** from live video with bounding boxes and live labels overlaid on the frame.

---

## 🎯 Detected Emotions

| # | Emotion | # | Emotion |
|---|---------|---|---------|
| 1 | 😡 Angry | 5 | 😢 Sad |
| 2 | 🤢 Disgust | 6 | 😲 Surprise |
| 3 | 😨 Fear | 7 | 😐 Neutral |
| 4 | 😄 Happy | | |

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| **Language** | Python 3.8+ |
| **Face Detection** | OpenCV (`haarcascade_frontalface_default.xml`) |
| **Emotion Model** | Keras / TensorFlow (`emotion_model.hdf5`) |
| **Image Processing** | NumPy, OpenCV |
| **Webcam Capture** | OpenCV VideoCapture (Mac compatible via `CAP_AVFOUNDATION`) |

---

## 📁 Project Structure

```
emotion-detection/
├── emotion_detection.py                  # Main script — run this
├── emotion_model.hdf5                    # Pre-trained Keras emotion model
├── haarcascade_frontalface_default.xml   # OpenCV face detection classifier
└── README.md                             # This file
```

---

## ⚙️ How It Works

```
Webcam Frame
    │
    ▼
Convert to Grayscale
    │
    ▼
Face Detection (Haar Cascade)
    │
    ▼
Crop & Resize ROI → 64×64 px
    │
    ▼
Normalize Pixel Values (÷ 255)
    │
    ▼
Reshape → (1, 64, 64, 1) for model input
    │
    ▼
Keras Model Prediction (7 emotion classes)
    │
    ▼
Display: Bounding Box + Emotion Label on Frame
```

1. Each webcam frame is converted to **grayscale** for face detection.
2. **Haar Cascade** detects face regions and extracts the Region of Interest (ROI).
3. The ROI is **resized to 64×64**, normalized, and reshaped for the Keras model.
4. The model outputs probabilities for all 7 emotions — the highest-confidence label is displayed live on screen.

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/programmer-akash/AI_ML_TRAINING.git
cd AI_ML_TRAINING/emotion-detection
```

### 2. Install Dependencies

```bash
pip install opencv-python numpy keras tensorflow
```

> **Mac users:** OpenCV's `CAP_AVFOUNDATION` backend is already configured in the script for webcam compatibility.

### 3. Run the Project

```bash
python emotion_detection.py
```

- A webcam window titled **"Emotion Detection System"** will open.
- Detected faces will have a **green bounding box** with the **emotion label** shown above.
- Press **`q`** to quit.

---

## 📋 Requirements

```
python >= 3.8
opencv-python
numpy
keras
tensorflow
```

---

## 📸 Sample Output

```
┌─────────────────────────────────┐
│                                 │
│      Happy                      │
│   ┌───────────┐                 │
│   │  😄 Face  │                 │
│   └───────────┘                 │
│                                 │
│   Emotion Detection System      │
└─────────────────────────────────┘
```

> *Green bounding box drawn around each detected face with the predicted emotion label displayed above it.*

---

## 🔑 Key Highlights

- ✅ **No DeepFace** — lightweight and fast, runs entirely on OpenCV + Keras
- ✅ **Real-time processing** — frame-by-frame webcam feed analysis
- ✅ **Mac compatible** — uses `cv2.CAP_AVFOUNDATION` for reliable webcam access on macOS
- ✅ **7-class classification** — covers the full spectrum of basic human emotions
- ✅ **Modular design** — easy to swap the model or extend emotion labels

---

## 🎓 Learning Outcomes

Working on this project helped me understand:

- How **Haar Cascade classifiers** work for face detection
- How to preprocess image data (resize, normalize, reshape) for deep learning inference
- How to load and use a **pre-trained Keras model** for real-time predictions
- How to overlay **text and bounding boxes** on live video frames using OpenCV
- How to handle a **real-time video loop** with proper release and cleanup

---

## 🌐 Connect with Me

<div align="center">

| Platform | Link |
|---|---|
| 🌐 **Portfolio** | [programmer-akash.github.io/portfolio](https://programmer-akash.github.io/portfolio/) |
| 🐙 **GitHub** | [github.com/programmer-akash](https://github.com/programmer-akash) |
| 💼 **LinkedIn** | [linkedin.com/in/coder-akash-halder](https://www.linkedin.com/in/coder-akash-halder/) |
| 📧 **Email** | akashhalder.me.7410@gmail.com |

</div>

---

<div align="center">

⭐ *If this project helped you, consider giving it a star!*

</div>
