# 🚦 Video-Based Traffic Surveillance System

This project presents a real-time, automated **Traffic Surveillance System** that detects **traffic violations**, **accidents**, and performs **traffic flow analysis** using deep learning and computer vision techniques on live or recorded video feeds. The system utilizes a combination of YOLOv8, Deep SORT, ByteTrack, MobileNetV2, and EasyOCR to provide a comprehensive, scalable solution for smarter traffic law enforcement.

## 📌 Key Features

-  Vehicle detection using **YOLOv8**
-  Multi-object tracking with **Deep SORT** and **ByteTrack**
-  Accident classification using **MobileNetV2**
-  License plate recognition via **EasyOCR**
- Speed estimation using motion analysis
- Traffic flow analysis (Free Flow / Moderate / Congested)
- **Email and SMS alerts sent to the nearest police station** when violations are detected
-  Real-time visualization with OpenCV overlays

---

## 🧠 Technologies Used

| Task                        | Technology / Framework |
|-----------------------------|-------------------------|
| Vehicle Detection           | YOLOv8 (Ultralytics)    |
| Object Tracking             | Deep SORT, ByteTrack   |
| Incident Classification     | MobileNetV2             |
| License Plate Recognition   | EasyOCR                 |
| Notification System         | SMTP (Email), Twilio (SMS) |
| Visualization               | OpenCV                  |
| Backend Language            | Python 3.8+             |
| Deep Learning Framework     | PyTorch                 |

---

## 🛠️ Project Modules

### 1.  Frame Extraction
Extracts every 30th frame from raw traffic videos using OpenCV. Frames are categorized for training accident classifier models.

### 2.  Vehicle Detection (YOLOv8)
Detects various vehicle types (car, truck, bus, motorcycle) in each video frame.

### 3. Multi-Object Tracking (Deep SORT / ByteTrack)
Assigns unique IDs to track vehicles consistently across frames.

### 4.  Incident Classification (MobileNetV2)
Classifies accidents such as:
- Rear-end collision
- Rollover
- Pedestrian hit
- Skidding
- Fire or explosion
- Head-on collision

### 5. License Plate Recognition (EasyOCR)
Detects and reads license plates from cropped vehicle regions for identification.

### 6.  Speed Estimation
Estimates vehicle speeds by tracking movement across frames using centroid displacement.

### 7.  Traffic Flow Analysis
Monitors the density and speed of vehicles to classify traffic as:
- `Free Flow`
- `Moderate`
- `Congested`

### 8.  Email & SMS Alerts to Police Stations
When an accident is detected:
- An **email** is sent with the incident details, vehicle info, and video snapshot.
- An **SMS alert** is sent using Twilio or similar service with a quick summary and GPS coordinates.
- Contact information for the nearest police station is retrieved via geolocation services or pre-configured.

---

## 🚀 How to Run



# Install required dependencies
pip install -r requirements.txt

# Add your credentials in config/notification_config.py (Email, SMS API)

# Run the main application
python main.py
