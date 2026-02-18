# 🚗 AI Self-Driving Cars — Autonomous Driving Stack

![Python](https://img.shields.io/badge/Python-3.10-blue)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## 📌 Problem Statement
Implementing core components of an autonomous driving stack including lane detection,
perspective transform, basic perception and PID control simulation using Python and OpenCV.

---

## 🛠️ Tech Stack
| Category | Tools |
|----------|-------|
| Language | Python 3.10 |
| Vision Library | OpenCV |
| Libraries | NumPy, Matplotlib |
| Platform | Google Colab |

---

## 📁 Project Structure
```
AI-Self-Driving-Cars/
│
├── AI_Self_Driving_Cars.ipynb     # Main notebook
├── README.md                      # Project documentation
├── test_images/                   # Input road images
│   ├── road1.jpg
│   ├── road2.jpg
│   └── road3.jpg
└── output_images/                 # Generated outputs
    ├── pipeline_summary.png
    ├── all_lane_results.png
    ├── pid_controller.png
    ├── perspective_transform.png
    └── video_frames.png
```

---

## 🔧 Pipeline Steps

### 1. 🖼️ Grayscale + Gaussian Blur
Convert image to grayscale and reduce noise using Gaussian blur (kernel size 5).

### 2. 🔍 Canny Edge Detection
Detect edges in the image using Canny algorithm.
- Low threshold: 50
- High threshold: 150

### 3. 📐 Region of Interest (ROI)
Apply trapezoidal mask to focus only on the road area ahead.

### 4. 📏 Hough Transform
Detect straight lane lines from edge image.
- rho = 2, theta = π/180
- Threshold = 20, MinLineLen = 40

### 5. 🦅 Perspective Transform
Apply Bird's Eye View transformation to get top-down road view.

### 6. 🎨 Color Segmentation
Detect white and yellow lane lines using HLS color masking.

### 7. 🎮 PID Controller
Simulate lane-keeping steering using Proportional-Integral-Derivative controller.
- Kp = 0.5, Ki = 0.01, Kd = 0.1

### 8. 🎥 Video Processing
Apply full lane detection pipeline frame by frame on dashcam video.

---

## 📊 Results

### Full Pipeline Summary
![Pipeline](output_images/pipeline_summary.png)

### Lane Detection on Test Images
![Lane Results](output_images/all_lane_results.png)

### PID Controller Simulation
![PID](output_images/pid_controller.png)

### Perspective Transform
![Perspective](output_images/perspective_transform.png)

---

## 📈 Evaluation
| Metric | Result |
|--------|--------|
| Detection Rate | 100% on test images |
| Avg Lines Detected | 8+ per image |
| Video FPS | 20 FPS |
| PID Convergence | < 2 seconds |

---

## ▶️ How to Run
1. Open `AI_Self_Driving_Cars.ipynb` in Google Colab
2. Click **Runtime → Run All**
3. Dataset & images download automatically
4. All output images saved to `output_images/`

---

## 🌍 Real-World Applications
- ADAS (Advanced Driver Assistance Systems)
- Robotics navigation
- Dashcam video processing
- Autonomous vehicle prototyping

---

## 👩‍💻 Author
**Kanna Bhavya Sree**
[GitHub Profile](https://github.com/kannabhavyasree)
