
# 🖐️ AI-Based Invisible Hand for Disabled People

**An intelligent computer control system for people with disabilities using facial gestures—blink to click, head tilt to move cursor, and open mouth to scroll. Powered by Computer Vision and Python. No hardware, just a webcam!**

---

## 🔍 Overview

This project presents a hands-free, AI-powered interface that allows users—especially individuals with motor disabilities—to interact with a computer using facial gestures. It uses real-time facial landmark detection to control mouse movements and simulate click and scroll actions.

### 🎯 Key Features

- 👁️ Blink left/right eye to simulate mouse left/right click  
- 🧠 Head tilt controls cursor movement direction  
- 👄 Open mouth to trigger scrolling mode (up/down based on nose position)  
- 📈 Calibration-based EAR & MAR threshold tuning for gesture accuracy  
- ⚡ Real-time processing using only a webcam

---

## 🛠️ Technologies Used

- Python 3
- OpenCV
- Dlib (with shape predictor)
- PyAutoGUI
- Imutils
- NumPy, SciPy, Matplotlib

---

## ⚙️ Installation & Setup

1. **Install dependencies**

   Use the provided `requirements.txt` file to install all necessary Python packages:

   ```bash
   pip install -r requirements.txt
````

2. **Download and place the shape predictor file**

   Download the `shape_predictor_68_face_landmarks.dat` model from the [official dlib website](http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2), extract it, and place it in the root folder of this project (same level as `project.py`).

3. **Run the application**

   Simply run the main Python file:

   ```bash
   python project.py
   ```

---

## 📁 Project Structure

```
invisible-hand/
│
├── project.py               # Main calibration + real-time gesture control code
├── requirements.txt         # All required Python libraries
├── shape_predictor.dat      # Dlib’s face landmark model (external file)
├── VDP.py                   # Color-based drawing (optional, experimental)
├── hough.py                 # Hough line transform demo (optional, experimental)
```

---

## 🧪 How It Works

### 🔹 Phase I – Calibration (First 25 seconds)

* Records facial gesture data for:

  * Both eyes open
  * Left eye closed (for left click)
  * Right eye closed (for right click)
  * Mouth open (for scrolling)
* Plots real-time graphs to visualize EAR and MAR values
* Calculates median thresholds for each gesture

### 🔹 Phase II – Real-Time Gesture Control

* Tracks facial landmarks using webcam
* Calculates EAR (Eye Aspect Ratio) & MAR (Mouth Aspect Ratio)
* Uses the calibrated thresholds to trigger:

  * 🖱️ Left click → left eye blink
  * 🖱️ Right click → right eye blink
  * ➕ Mouse movement → nose direction from screen center
  * 🔃 Scroll mode toggle → open mouth
  * ⬇️⬆️ Scroll direction → nose up/down tilt while in scroll mode

---

## 🧠 Algorithms & Logic

* **EAR (Eye Aspect Ratio)**: Detects eye closure or blink
* **MAR (Mouth Aspect Ratio)**: Detects mouth open gesture
* **Facial Landmarks**: Extracted using Dlib’s 68-point face shape predictor
* **Convex Hulls**: Used to outline facial features like eyes and mouth
* **Angle Detection**: Nose tip relative to center to detect direction of movement
* **PyAutoGUI**: Simulates real mouse movements and clicks

---

## ✅ Applications

* 💻 Assistive technology for people with motor or physical disabilities
* 🧪 Touchless computer interface for labs, hospitals, or cleanrooms
* 🕹️ Accessible gaming for people with limited mobility
* 🌐 Hands-free navigation for public kiosks or accessibility UI testing

---
