# 🧠 AI Sentinel — Deepfake Video Detection Web App

AI Sentinel is a Flask-based web application that detects whether a video is **REAL** or **FAKE (Deepfake)** using a deep learning model built with **ResNeXt50 + LSTM** architecture.

The system analyzes facial inconsistencies across video frames to determine deepfake manipulation with a confidence score.

---

## 🚀 Features

- Upload any video for deepfake detection
- Automatic face extraction from video frames
- CNN + LSTM model for spatial and temporal analysis
- REAL / FAKE prediction with confidence percentage
- Clean web interface using Flask + Tailwind CSS

---

## 🏗️ Project Structure

```
aisentinel/
│
├── app.py                  # Flask server & inference pipeline
├── model/
│   └── df_model.pt         # Trained deepfake detection model (NOT in repo)
│
├── templates/
│   └── index.html          # Frontend UI
│
├── static/
│   └── images/             # Images used in UI
│
├── Uploaded_Files/         # Temporary storage for uploaded videos
├── .gitignore
└── README.md
```

---

## 🔗 How Components Work Together

### `app.py`
- Runs the Flask web server
- Accepts video upload
- Extracts frames using OpenCV
- Detects faces using `face_recognition`
- Loads trained model from `model/df_model.pt`
- Predicts REAL or FAKE
- Sends result to UI

### `templates/index.html`
- Web interface built using Tailwind CSS

### `static/images`
- UI illustrations and assets

### `model/df_model.pt`
- Pretrained PyTorch model (too large for GitHub)

### `Uploaded_Files`
- Temporarily stores uploaded videos (deleted after processing)

---

## 🧠 Deep Learning Model Architecture

- **ResNeXt50 (CNN)** → Extracts facial features from each frame
- **LSTM (RNN)** → Learns temporal inconsistencies across frames
- **Softmax** → Outputs REAL or FAKE with confidence

---

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| Python | Core programming |
| Flask | Web framework |
| PyTorch | Deep learning inference |
| OpenCV | Frame extraction |
| face_recognition / dlib | Face detection |
| Tailwind CSS | Frontend styling |

---

## ⚠️ Model File (Important)

The trained model is not included due to GitHub size limits.

📥 Download model from:  
**PASTE YOUR GOOGLE DRIVE LINK HERE**

After downloading, place it in:

```
aisentinel/model/df_model.pt
```

---

## ▶️ How to Run

### 1️⃣ Clone repository
```bash
git clone https://github.com/yourusername/ai-sentinel-deepfake-detection.git
cd ai-sentinel-deepfake-detection
```

### 2️⃣ Create virtual environment
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3️⃣ Install dependencies
```bash
pip install flask torch torchvision opencv-python numpy scikit-image face_recognition dlib
```

### 4️⃣ Add model file to `model/` folder

### 5️⃣ Run the app
```bash
python app.py
```

Open:
```
http://localhost:5000
```

---

## 📌 Notes

- Works on CPU
- Short videos (5–10s) recommended
- First run may take time due to model loading

---

## 🎯 Future Improvements

- Real-time webcam detection
- Frame heatmaps
- Docker deployment

---

## 👨‍💻 Author

**Sidharth Bhangalia**
