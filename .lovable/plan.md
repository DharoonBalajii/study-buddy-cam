

# Plan: Generate Pure C++ OpenCV Project Files

## Overview
Generate all C++ source files as downloadable artifacts in `/mnt/documents/emotion_study_assistant/`. No web files, no JavaScript, no HTML — only `.cpp` and `.h` files plus a setup README. The project runs natively on your laptop using your webcam via OpenCV's GUI window (`cv::imshow`).

## Files to Create (9 files)

| File | Purpose |
|------|---------|
| `main.cpp` | Main loop: webcam capture, keyboard input (q=quit, m=toggle mode), coordinates all modules |
| `face_detection.h` | FaceDetector class declaration |
| `face_detection.cpp` | Haar Cascade face detection implementation |
| `emotion_simulator.h` | EmotionSimulator class declaration |
| `emotion_simulator.cpp` | Random emotion generation (Happy/Sad/Angry/Neutral/Sleepy) |
| `decision_engine.h` | DecisionEngine class declaration |
| `decision_engine.cpp` | Emotion-to-suggestion mapping + Strict/Relaxed mode |
| `productivity_tracker.h` | ProductivityTracker class declaration |
| `productivity_tracker.cpp` | Score calculation, study timer, log.txt writing, session summary |

Plus one `README_SETUP.txt` with install instructions for Windows/Mac/Linux.

## All Features Included
- Webcam face detection with rectangle overlay
- Simulated emotion (random from 5 options)
- Study suggestions on screen
- Productivity score: `(focused / total) * 100`
- Study timer (auto start/stop with face)
- "User not present" warning
- "BEEP!" console alert for Sleepy/Angry
- log.txt emotion logging via `ofstream`
- Strict/Relaxed mode toggle (press 'm')
- Session summary printed on quit (press 'q')

## What You Install on Your Laptop
- **Windows**: MinGW (g++) + OpenCV → instructions in README
- **Mac**: `brew install opencv`
- **Linux**: `sudo apt install g++ libopencv-dev`
- Copy `haarcascade_frontalface_default.xml` to project folder (path in README)

## Compile & Run
```
g++ main.cpp face_detection.cpp emotion_simulator.cpp decision_engine.cpp productivity_tracker.cpp -o app `pkg-config --cflags --libs opencv4`
./app
```

## Technical Notes
- All display via `cv::imshow` (native OpenCV window) — no browser needed
- Uses only standard C++ and OpenCV — no other dependencies
- OOP structure with classes, header files, clean separation
- Beginner-level code with comments explaining each step
- Will remove/ignore all existing web project files — output is purely C/C++

