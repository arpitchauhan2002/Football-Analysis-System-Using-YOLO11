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
```
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
```
## ⚙️ Setup Instructions

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/arpitchauhan2002/Football-Analysis-System-Using-YOLO11.git
cd Football-Analysis-System-Using-YOLO11
```
### 2️⃣ Create and Activate Virtual Environment (Recommended)

```bash
python -m venv venv

# On Windows

venv\Scripts\activate

# On Unix/macOS
source venv/bin/activate
```
### 3️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```
**Or install manually:**
```bash
pip install opencv-python torch torchvision numpy pillow scikit-learn ultralytics
```

### 4️⃣ Model Setup

Download the trained YOLOv11 model weights (best.pt) generated from your training script or i have given the drive link to download the model:
```bash
model/
└── best.pt

If you're using an external model link, download and store the weights in the model/ folder manually.
---

### ▶️ Running the Code

### 1. Detection Using Pretrained YOLOv11
```bash
from ultralytics import YOLO

# Load the YOLOv11 model (pretrained or custom trained)
model = YOLO("yolo11l.pt")  # Use "model/best.pt" for trained version

# Run detection on sample video
results = model.predict(source="input_video/15sec_input_720p.mp4", save=True)

```
- Outputs: Detected video is saved in runs/detect/predict/

### 2. Tracking and Player Re-Identification
```bash
After replacing with your trained model:
model = YOLO("model/best.pt")  # Your fine-tuned YOLOv11 model
results = model.track(source="input_video/15sec_input_720p.mp4", save=True, persist=True)

```
- Annotated video with player IDs: runs/track/predict/
- Frame-wise results or Re-ID metadata: tracker_stubs/player_detection.pkl
---

### 🧾 Dependencies
- Python 3.8+
- OpenCV
- Ultralytics (YOLOv8)
- Torch + TorchVision
- Torchreid
- scikit-learn
- Pillow

---
