# Predicting-Biomechanical-Risk-Factors-for-Division---I-Women-s-Basketball-Athletes

Our proposed approach leverage video analysis and computer vision to assist coaches, trainers, and sports scientists in the early detection and prevention of lower extremity injuries, particularly ACL injuries. This framework provides an affordable, real-time, and automated alternative to traditional biomechanical assessment.

---

## 📌 Table of Contents
- [Introduction](#introduction)
- [Objectives](#objectives)
- [Dataset Description](#dataset-description)
- [Methodology](#methodology)
- [Results](#results)
- [Future Work](#future-work)
- [Practical Application](#practical-application)
- [Dependencies & Tools](#dependencies--tools)
- [Getting Started](#getting-started)
- [License and Acknowledgments](#license-and-acknowledgments)

---

## 📖 Introduction

Basketball involves high-impact movements such as jump landings, which pose significant injury risks. Traditional biomechanical assessments are expensive and time-consuming.  
We introduce an automated, affordable, and real-time solution using computer vision.

### Core Contributions

- 📊 Labeled dataset of NCAA Division I female basketball athletes performing countermovement jumps (CMJs)
- 🎯 YOLO-based object detection and semantic segmentation for biomechanical risk factor identification
- 📈 Performance analysis across YOLO variants and related models
- 🏃‍♀️ Deployment framework for real-time injury prevention applications

---

## 🎯 Objectives

- Develop a high-quality annotated dataset for biomechanical risk assessment
- Automate feature extraction of risk-related metrics from video data
- Evaluate YOLO-based models for detecting biomechanical errors
- Design a real-time injury risk prediction system for sports training environments

---

## 📂 Dataset Description

- **Participants:** 17 NCAA Division I female basketball athletes  
- **Frames:** 86,000+ frames (frontal + lateral views) during CMJs  
- **Annotations:** Six biomechanical risk factors:  
  - Knee Flexion  
  - Lateral Trunk Flexion  
  - Foot Landing Symmetry  
  - Trunk Flexion  
  - Ankle Plantar Flexion  
  - Stance Width  
- **Processing:** Frames resized to 640×640 px, segmented into 200 frames per video, camera tilt correction applied  

---

## ⚙️ Methodology

### 📽 Video & Image Processing
- Frame extraction from high-resolution videos
- Camera tilt correction for consistency
- Keypoint detection using MediaPipe Pose

### 🧠 Object Detection & Segmentation
- Models: YOLOv5n, YOLOv5nu, YOLOv8n, YOLOv10n, YOLOv3 Tiny, Mask R-CNN, Darknet
- Metrics: Precision, Recall, mAP@0.5  
- **Best model:** YOLOv5nu (+13.9% accuracy over YOLOv8n)

### 📝 Error Annotation Algorithm
- Automates bounding box creation from extreme keypoint coordinates
- Focuses on lower body regions for accurate biomechanical analysis

### 🔧 Training & Evaluation
- Transfer learning from YOLO pre-trained weights
- Multi-object detection to identify postural errors

---

## 📊 Results

| Metric | Performance |
|---------|-------------|
| Stance Width, Trunk Flexion, Knee Flexion | High accuracy |
| Foot Landing Symmetry | Moderate accuracy |
| Ankle Plantar Flexion | Lower accuracy (occlusion challenges) |
| **mAP@0.5** | ~87.9% average |

---

## 🔮 Future Work

- Address data imbalance and occlusion issues
- Expand dataset with multi-view camera setups
- Deploy on mobile devices for real-time use
- Explore transferability to public datasets

---

## 🏟 Practical Application

The proposed approach enables:
- Real-time biomechanical assessment during training
- Injury prevention support for basketball athletes
- Automated error detection, reducing manual workload
- Quantitative feedback for coaches and sports scientists

---

## 🛠 Dependencies & Tools

- Python 3.x  
- PyTorch  
- YOLOv5  
- MediaPipe  
- OpenCV  
- NumPy  
- Roboflow Semantic Segmentation  
- Other standard Python libraries  

---

## 🚀 Getting Started

### 1️⃣ Clone the repository
```bash
git clone https://github.com/yourusername/BioJump.git
cd BioJump
