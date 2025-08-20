
---

# Sign Language Detection

This project uses a classic machine learning approach to detect the sign language from the hand gestures by using the webcamera. The goal is to build a system that can remove the communication gap for the people with hearing and speech difficulties.

---

## Features

- Real-time gesture detection using a webcam.
- Detects custom hand gestures (trained on your own dataset).
- Displays the recognized gesture.
- Uses MediaPipe for accurate hand tracking.
- Built with TensorFlow for Machine Learning predictions.

---

## Dataset

This project uses my own dataset of hand gestures. I collected the hand gestures(1385 images of total 5 categories) using my web camera and trained them using google teachable machine. After that i exported them as keras model and use them.

- **Source:** [Dataset Google Drive](https://drive.google.com/file/d/1G2exjkMMH_ZecFawdjA1PCsU-Lppsv3W/view?usp=sharing)
- **File:** `keras_model.h5`

---

## Requirements

| Library / Tool | Version   |
| -------------- | --------- |
| Python         | 3.11.7    |
| TensorFlow     | 2.12.1    |
| MediaPipe      | 0.10.18   |
| OpenCV-Python  | 4.10.0.84 |
| NumPy          | latest    |
| CVZone         | latest    |

---

## Installation

1. **Clone the repository:**

```bash
git clone https://github.com/Pranto-Bapary/Sign-Language-Detection.git
cd sign-language-detection
```

2. **Create a virtual environment:**

```bash
python -m venv venv
```

3. **Activate the virtual environment:**

```bash
# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate
```

4. **Upgrade pip:**

```bash
pip install --upgrade pip
```

5. **Install required packages:**

```bash
pip install tensorflow==2.12.1 mediapipe==0.10.18 opencv-python==4.10.0.84 numpy cvzone
```

---

## Workflow

The project follows a real-time machine learning pipeline for sign language detection:

- **Data Collection & Model Preparation:**

  - The TensorFlow model is trained on **custom hand gesture images** collected specifically for this project.
  - Each gesture (e.g., "Thank You", "Hello") has multiple images for better generalization.

- **Webcam Input & Hand Detection:**

  - The application accesses the webcam using OpenCV.
  - MediaPipe's Hand Tracking module detects and tracks hand landmarks in real-time.

- **Feature Extraction & Preprocessing:**

  - Hand landmarks are extracted as keypoints (x, y coordinates).
  - Keypoints are normalized and reshaped to match the TensorFlow model input format.

- **Gesture Prediction:**

  - Pre-processed features are fed into the TensorFlow model.
  - The model predicts the gesture and outputs a confidence percentage for each gesture.

- **Output Display:**

  - The predicted gesture is displayed on the screen along with the confidence score (e.g., "Thank You – 92%").
  - Real-time feedback allows users to see gestures detected live as they perform them.

- **Optional Enhancements:**

  - Detect multiple gestures in sequence.
  - Apply thresholds to filter low-confidence predictions.

---

## Usage

1. Activate your virtual environment.
2. Run the main Python script:

```bash
python main.py
```

3. Perform hand gestures in front of the webcam.
4. The predicted gesture and confidence will be displayed in real-time.

---
