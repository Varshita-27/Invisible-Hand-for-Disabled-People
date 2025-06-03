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

## ⚙️ Installation

1. **Install dependencies**

   pip install -r requirements.txt
Download shape predictor 

(Due to size constraints, this file isn't stored in the repo. You can download it from: http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2)

Place shape_predictor_68_face_landmarks.dat in the root directory

Run the application

python project.py
📁 Folder Structure
invisible-hand/
│
├── project.py               # Main calibration + real-time control logic
├── requirements.txt         # Python package requirements
├── shape_predictor.dat      # Dlib face landmark model (external)
├── VDP.py                   # Color-based drawing (experimental)
├── hough.py                 # Hough line transform demo (experimental)
🧪 How It Works
Phase I – Calibration (First 25 seconds)
Records EAR and MAR values for:

Both eyes open

Left eye blink

Right eye blink

Open mouth

Displays real-time plots to visualize gesture thresholds

Phase II – Gesture Control
Uses calibrated EAR & MAR values to trigger:

Left click (left eye blink)

Right click (right eye blink)

Mouse movement (nose tracking)

Scroll mode (mouth open toggle + head tilt)

🧠 Algorithms Used
EAR (Eye Aspect Ratio) – to detect eye blinks

MAR (Mouth Aspect Ratio) – to detect mouth opening

68-point facial landmark detection – via Dlib

Angle calculation – nose to screen center vector for direction

PyAutoGUI – to simulate actual mouse and scroll events

✅ Applications
Assistive technology for people with motor disabilities

Hands-free computer control in public/sterile environments

Accessibility tools for UI testing and remote systems

Gamified accessibility for education and entertainment

