# 🎓 Study Buddy Cam: Emotion-Based Study Assistant

![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)

Welcome to **Study Buddy Cam**, your intelligent, emotion-based study assistant! This project leverages the power of C++ and OpenCV for real-time facial detection and provides smart study recommendations based on simulated emotional analysis. A companion Web UI is also included for a seamless interactive experience.

## ✨ Features

- **Real-Time Face Detection**: Uses Haar Cascades to reliably track your face while studying.
- **Emotion Simulation**: Intelligent simulation of your mood to adapt study suggestions.
- **Dynamic Decision Engine**: Switches between *Strict* and *Relaxed* modes to keep your study sessions productive but balanced.
- **Productivity Tracking**: Logs your session times, calculates scores, and outputs a detailed session summary to `log.txt`.
- **Interactive Web UI**: A beautiful front-end interface built with HTML/CSS to manage your study sessions visually.

## 📂 Project Structure

| File | Purpose |
|------|---------|
| `main.cpp` | Main program loop handling the webcam feed and keyboard events. |
| `face_detection.h / .cpp` | Face detection implementation using OpenCV Haar Cascade. |
| `emotion_simulator.h / .cpp` | Logic for generating emotion-based states. |
| `decision_engine.h / .cpp` | Handles study suggestions, mode toggling, and core logic. |
| `productivity_tracker.h / .cpp` | Tracks session scores, timers, and handles file logging. |
| `index.html` | The visually stunning web interface. |

## 🚀 Setup & Installation

Detailed setup instructions can be found in `README_SETUP.txt`. Below is a quick overview:

### Prerequisites
- **Windows**: Install MinGW and OpenCV (ensure OpenCV binaries are in your PATH).
- **macOS**: `brew install opencv`
- **Linux (Ubuntu/Debian)**: `sudo apt update && sudo apt install g++ libopencv-dev`

> **IMPORTANT**: You must copy `haarcascade_frontalface_default.xml` (provided by OpenCV) into the same folder as the `.cpp` files to enable face detection.

## 💻 Compile & Run

Open your terminal and run the following commands:

**macOS & Linux**:
```bash
g++ main.cpp face_detection.cpp emotion_simulator.cpp decision_engine.cpp productivity_tracker.cpp -o app `pkg-config --cflags --libs opencv4`
./app
```

**Windows** (Adjust paths depending on your OpenCV version):
```cmd
g++ main.cpp face_detection.cpp emotion_simulator.cpp decision_engine.cpp productivity_tracker.cpp -o app.exe -IC:\opencv\build\include -LC:\opencv\build\x64\vc16\lib -lopencv_world490
app.exe
```

## 🎮 Controls

While the camera window is active:
- `m` / `M` : Toggle between **Strict** and **Relaxed** mode.
- `q` / `Q` : Quit the application and generate a session summary in `log.txt`.

## 📈 Logging

All sessions are automatically logged. You can review `log.txt` after quitting to see a breakdown of your detected emotions, session duration, and overall productivity score.
