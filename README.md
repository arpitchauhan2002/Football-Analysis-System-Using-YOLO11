# ⚽ Football Broadcast Player Detection & Re-Identification using YOLOv11

This repository presents a system for detecting and re-identifying players in football match broadcasts. The model is custom-trained on an annotated dataset using YOLOv11 and includes a tracking pipeline for player association across video frames.

## 📽️ Demo Showcase

### 🟡 Inference Using Pretrained YOLOv11
[![Pretrained YOLOv11 Detection](https://img.youtube.com/vi/hH7oUJr69xg/maxresdefault.jpg)](https://youtu.be/hH7oUJr69xg)
🔗 https://youtu.be/hH7oUJr69xg  
📌 *Football Player Detection in Broadcast Footage | Pretrained YOLOv11 Inference Demo*

---

### 🟢 Inference Using Custom Trained YOLOv11
[![Custom Trained YOLOv11 Tracking](https://img.youtube.com/vi/k6hgFCCpIeE/maxresdefault.jpg)](https://youtu.be/k6hgFCCpIeE)  
🔗 https://youtu.be/k6hgFCCpIeE  
📌 *Custom Trained YOLOv11 Model for Football Player Detection | Re-ID and Tracking Demo*

---
## 📂 Project Overview

This project enables:
- ⚡ Real-time detection of players, referee, football, and objects
- 🏷️ Re-identification of players across frames using tracking
- 🎥 Generation of output videos with bounding boxes and identities
- 📁 Saving detection and tracking results as `.pkl` files

---

📦 Directory Structure
---
.
├── input_video/               # Source input video
├── model/                     # Model export or download link
├── notebook_for_training_the_model/
│   └── Football_Analysis_System (1).ipynb
├── output_videos/sf/          # Output results
├── tracker_stubs/             # .pkl file for tracking results
├── trackers/                  # Custom tracker logic
├── utils/                     # Utility functions
├── yolo_inference.py          # YOLO detection logic
├── main.py                    # Entry point script
├── requirements.txt           # Python dependencies
└── README.md                  # You are here
---
