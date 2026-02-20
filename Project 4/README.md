<div align="center">

# 🎯 Face Detection System

[![Portfolio](https://img.shields.io/badge/🌐_Portfolio-Live-7C4DFF?style=for-the-badge)](https://programmer-akash.github.io/portfolio/)
[![GitHub](https://img.shields.io/badge/GitHub-programmer--akash-181717?style=for-the-badge&logo=github)](https://github.com/programmer-akash)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-coder--akash--halder-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/coder-akash-halder/)
![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

*A real-time face detection application built with Python and OpenCV, using the Haar Cascade Classifier to detect and highlight faces through a webcam feed.*

</div>

---

## 📸 Demo

The system draws a green bounding box around every detected face in real time, along with a live face count overlay on the screen.

<img width="652" height="447" alt="image" src="https://github.com/user-attachments/assets/455e2667-1a09-498e-bb30-061ac148261d" />

---

## ✨ Features

- **Real-time face detection** via webcam using OpenCV's Haar Cascade model
- **Live face counter** displayed on the video feed
- **Snapshot capture** — save the current frame as a `.jpg` with a keypress
- **Lightweight & dependency-free** beyond OpenCV — no deep learning framework required

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.x | Core language |
| OpenCV (`cv2`) | Computer vision & webcam I/O |
| Haar Cascade Classifier | Pre-trained face detection model |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.x installed
- A working webcam

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/programmer-akash/AI_ML_TRAINING.git
   cd AI_ML_TRAINING/face-detection
   ```

2. **Install dependencies**
   ```bash
   pip install opencv-python
   ```

### Running the App

```bash
python3 face_detection.py
```

---

## 🎮 Controls

| Key | Action |
|-----|--------|
| `s` | Save the current frame as `captured_face.jpg` |
| `q` | Quit the application |

---

## ⚙️ Configuration

You can tweak detection sensitivity inside `face_detection.py`:

```python
faces = face_cascade.detectMultiScale(
    gray,
    scaleFactor=1.3,   # How much the image is reduced at each scale (higher = faster, less accurate)
    minNeighbors=5     # How many neighbor rectangles needed to confirm a face (higher = fewer false positives)
)
```

**Webcam index** — if your webcam isn't detected, change the device index:

```python
cap = cv2.VideoCapture(0)  # Try 0, 1, or 2 depending on your system
```

> **macOS users:** The script uses `cv2.CAP_AVFOUNDATION` as the backend, which is the recommended capture API for macOS.

---

## 📁 Project Structure

```
face-detection/
│
├── face_detection.py                     # Main application script
├── haarcascade_frontalface_default.xml   # Pre-trained face detection model
├── requirements.txt                      # Dependencies & setup instructions
└── README.md                             # Project documentation
```

---

## 🧠 How It Works

1. **Capture** — OpenCV opens the webcam and reads frames in a loop.
2. **Preprocess** — Each frame is converted to grayscale, which is what the Haar Cascade model expects.
3. **Detect** — The `detectMultiScale` function scans the grayscale frame at multiple scales to locate faces.
4. **Annotate** — Green rectangles are drawn around each detected face, and a face count is overlaid on the frame.
5. **Display** — The annotated frame is shown in a live window.

---

## 📦 Dependencies

```
opencv-python
```

Install with:

```bash
pip install opencv-python
```

---

## 🎓 Learning Outcomes

Building this project helped me understand:

- How **Haar Cascade classifiers** detect objects at multiple image scales
- How to process live **webcam frames** using OpenCV's VideoCapture loop
- How to **annotate video frames** with bounding boxes, labels, and counters
- How to handle **keypress events** for real-time interaction (snapshot, quit)
- How to manage **resource cleanup** (`cap.release()` and `destroyAllWindows()`)

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to open a pull request or file an issue.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

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

Built with 💜 by **Akash Halder** 

</div>
