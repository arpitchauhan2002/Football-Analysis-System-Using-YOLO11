# ⚽ Football Broadcast Player Detection & Re-Identification using YOLOv11

This repository presents a system for detecting and re-identifying players in football match broadcasts. The model is custom-trained on an annotated dataset using YOLOv11 and includes a tracking pipeline for player association across video frames.

## 📽️ Demo Showcase

### 🟡 Inference Using Pretrained YOLOv11
**📌 Football Player Detection in Broadcast Footage | Pretrained YOLOv11 Inference Demo**
[![Pretrained YOLOv11 Detection](https://img.youtube.com/vi/hH7oUJr69xg/maxresdefault.jpg)](https://youtu.be/hH7oUJr69xg)
🔗 https://youtu.be/hH7oUJr69xg  

---

### 🟢 Inference Using Custom Trained YOLOv11
📌**Custom Trained YOLOv11 Model for Football Player Detection | Re-ID and Tracking Demo**
[![Custom Trained YOLOv11 Tracking](https://img.youtube.com/vi/k6hgFCCpIeE/maxresdefault.jpg)](https://youtu.be/k6hgFCCpIeE)  
🔗 https://youtu.be/k6hgFCCpIeE  


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
**⚠️ Known Issue During requirements.txt Installation**
If you encounter the following error while installing dependencies:
```bash
Could not find a version that satisfies the requirement torch>=1.7.0 (from ultralytics->-r requirements.txt)
No matching distribution found for torch>=1.7.0
```
*✅ Fix: Ensure the following conditions are met before running pip install -r requirements.txt:*

- You are using Python 3.8 to 3.11 (preferably 64-bit)
- You have updated pip to the latest version

**Or install manually:**
```bash
pip install opencv-python torch torchvision numpy pillow scikit-learn ultralytics
```

### 4️⃣ Model Setup

You can run the system using two different approaches, depending on the model:

**🔹 Run with Pretrained YOLOv11 Model**

```bash
python yolo_inference.py
```
📌 Output:

- Player detections will be visible with simple bounding boxes and generic class names.
- Only numbers and approximate locations will be shown.
- No refined Re-ID or consistent player identification across frames.
  
**🟢 Run with Custom Trained YOLOv11 Model**
- After training your model on annotated football images (referee, football, players, etc.), place your best weights file here:
```bash
model/
└── best.pt
```
**📥 Note:**
- A direct download link for the trained model weights (best.pt) is provided inside the file:
```bash
model/model_link
```
-Please open the model_link file and download the model manually. Once downloaded, place it in the model/ folder.
-Or You Can You Your Own Model
**Then run the main pipeline using:**
```bash
python main.py
```
**📌 Output:**

- Players and referees are marked with consistent Re-ID numbers (as shown in the output image).
- Objects such as the football are accurately detected and tracked.
- Frame-by-frame tracking metadata is saved in tracker_stubs/player_detection.pkl.


### ▶️ Running the Code

**1. Detection Using Pretrained YOLOv11**

```bash
from ultralytics import YOLO

# Load the YOLOv11 model (pretrained or custom trained)
model = YOLO("yolo11l.pt")  # Use "model/best.pt" for trained version

# Run detection on sample video
results = model.predict(source="input_video/15sec_input_720p.mp4", save=True)

```
- Outputs: Detected video is saved in runs/detect/predict/

**2. Tracking and Player Re-Identification**

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
