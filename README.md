# 🚗 Lane and Traffic Sign Detection Web App  
### Lightweight Lane Detection (LaneNet) + YOLOv8 Object/Sign Detection  
**Tech Stack:** Flask • OpenCV • PyTorch • JavaScript • HTML/CSS

A real-time **ADAS (Advanced Driver Assistance System)** web application combining:

- **Lane detection** using a lightweight LaneNet segmentation model  
- **Traffic sign & object detection** using YOLOv8n  
- **Offset estimation**, curved lane overlays, and green lane-region visualization  
- **Live camera streaming** and **image upload processing**  
- **Full-stack architecture** using Flask (backend) and HTML/CSS/JS (frontend)  

This project demonstrates practical computer vision skills using both **deep learning** and **classical image processing techniques**.

---

## 📸 Demo Screenshots

### **Real-Time Lane + Sign Detection**
<img width="1366" height="768" alt="2025-11-20" src="https://github.com/user-attachments/assets/b880af57-309e-4797-b4ec-b566f40205f8" />

### **Detection on Uploaded Images**
<img width="1366" height="768" alt="2025-11-19 (20)" src="https://github.com/user-attachments/assets/0c232902-d5b4-44f5-9a69-18ec2891db14" />

### **UI (Idle State)**
<img width="1366" height="768" alt="2025-11-19 (19)" src="https://github.com/user-attachments/assets/01bbf550-e2a6-425c-a625-56477f6542dc" />

---

## ⭐ Features

### 🛣️ Lane Detection (LaneNet)
- Lightweight and fast lane segmentation  
- Lane mask → contour extraction → polynomial curve fitting  
- Smooth curved-lane rendering  
- Accurate offset estimation (“0.46m left/right”)  
- Green lane-region shading for visibility  

### 🚦 YOLOv8 Traffic Sign & Object Detection
Detects:  
- Cars  
- Bikes  
- Pedestrians  
- Road signs  
- Traffic lights  
- Any YOLO-supported class  

Each detection includes:  
- Class label  
- Confidence score  
- Bounding box  
- High-contrast color coding  

### 🖥️ Clean & Modern Frontend UI
- Dual-panel responsive layout  
- Real-time webcam detection  
- Road-image upload support  
- Adjustable frame interval  
- Displays detection count & processing time  

---

## 📁 Project Structure

```bash
lane-sign-app/
│
├── backend/
│   ├── app.py                 # Flask API server
│   ├── lanenet_model.py       # LaneNet model loader (PyTorch)
│   ├── postprocess.py         # Lane mask → lane curves + offset
│   ├── requirements.txt       # Backend dependencies
│   ├── models/
│   │    └── lanenet.pth       # LaneNet pretrained weights
│   └── yolov8n.pt             # YOLOv8n model file
│
├── frontend/
│   ├── index.html             # Main UI layout
│   ├── script.js              # Camera + API request logic
│   ├── styles.css             # Styling
│
└── README.md
🔧 Installation & Setup
1️⃣ Clone the repository
bash
Copy code
git clone https://github.com/<your-username>/lane-sign-app.git
cd lane-sign-app
2️⃣ Install backend dependencies
bash
Copy code
cd backend
pip install -r requirements.txt
3️⃣ Add the required models
Place the model files here:

bash
Copy code
backend/models/lanenet.pth  
backend/yolov8n.pt
4️⃣ Run the backend server
bash
Copy code
python app.py
5️⃣ Open the web application
cpp
Copy code
http://127.0.0.1:5000
🧠 How It Works
🔹 LaneNet Pipeline
Input frame (webcam or uploaded image)

LaneNet → segmentation mask

Contour extraction + filtering

Polynomial lane curve fitting

Lane region shading (green)

Offset calculated relative to frame center

Final overlay generated

🔹 YOLOv8 Pipeline
Detects vehicles, pedestrians, road signs, and lights

Draws bounding boxes with labels

Computes confidence scores

Returns detection stats

✔ Combined Output Includes:
Lane curves

Lane-region shading

Offset value

YOLO detections

Real-time FPS & processing time

📦 Backend Requirements
nginx
Copy code
flask
flask-cors
opencv-python
numpy
torch
ultralytics
🚀 Future Enhancements
Lane Departure Warning (LDW)

Traffic sign classification (speed limit, stop, etc.)

Traffic light color detection

Steering angle estimation

Enhanced night-mode lane detection

Mobile App (Flutter / React Native)

🤝 Contributing
Pull requests, issues, and improvements are welcome!
Feel free to open a PR anytime.

📝 License
This project is licensed under the MIT License, allowing free use, modification, and distribution with attribution.
