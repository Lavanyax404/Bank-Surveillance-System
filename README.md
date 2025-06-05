# 🛡️ GuardIQ - AI-Powered Surveillance System for Banks

GuardIQ is an intelligent surveillance system that leverages deep learning and computer vision to detect potential threats such as armed intruders, suspicious behavior, and emergencies within bank premises. It uses a custom-trained YOLOv8 model for real-time object detection and integrates with Telegram to send instant alerts to security personnel.

---

## 🚨 Key Features

- 🎯 **Real-Time Detection** of:
  - Gun
  - Knife
  - Masked individuals
  - Hands-up gesture (robbery indicator)
  - Security guards and normal persons

- 🧠 **YOLOv8 + Supervision Integration** for high-accuracy object tracking and annotation

- 📡 **Telegram Bot Integration** for instant alerts with image evidence

- 🕵️ **Multi-object Tracking** using ByteTrack

- 🗓️ **Timestamp Overlay** for evidence traceability

---

## 🔧 Requirements

Install dependencies:

```bash
pip install ultralytics supervision opencv-python requests
````

Ensure you have:

* Python 3.8+
* A webcam or a video file for input
* A trained YOLOv8 model (`best.pt`)

---

## 🤖 Setup Telegram Bot

1. Talk to [@BotFather](https://t.me/BotFather) and create a new bot.
2. Save the bot **token** and **chat ID**.
3. Replace the placeholders in `bot.py`:

```python
self.TOKEN = "YOUR_TOKEN_NUMBER"
self.CHAT_ID = CHAT_ID  # Replace with your numerical chat ID
```

---

## 🧠 Model Training (Optional)

If you'd like to train your own model using Ultralytics YOLOv8:

```bash
yolo task=detect mode=train model=yolov8n.pt data=data.yaml epochs=50 imgsz=640
```

---

## 💡 Threat Conditions Triggering Alerts

* **Gun + Mask** → Potential armed robbery
* **Knife** → Threat detected
* **Hands-up** → Emergency or robbery situation

Alerts are rate-limited to avoid spam (configurable in `bot.py`).

---

## 📽️ Output

* Saved video: `video/bank_robbery_detection.mp4`
* Alert snapshots: `alert.jpg` (temporary)

---
