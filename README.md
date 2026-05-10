# 🎓 Smart Classroom Assistant

> An AI-powered classroom management system combining **Face Recognition**, **Emotion Detection**, **Speech Recognition**, and **NLP Question Classification** — with a modern Flask web dashboard.

---

## 📌 Features

| Module | Description |
|--------|-------------|
| 👤 **Face Recognition** | Automatically detects and identifies students using DeepFace (VGG-Face model) |
| 😊 **Emotion Detection** | Analyzes student facial expressions in real-time during attendance |
| 🎙️ **Speech Recognition** | Captures spoken student questions via microphone using Google Speech API |
| 🧠 **NLP Classifier** | Classifies questions by subject using a TF-IDF + Naive Bayes pipeline |
| 🌐 **Web Dashboard** | Flask-powered UI for attendance records, Q&A logs, and face registration |

---

## 🗂️ Project Structure

```
Project/
├── Project.py               # Core CLI application (CV + Speech + NLP)
├── app.py                   # Flask web server
├── training_data.csv        # Training data for the NLP classifier
├── student_questions.csv    # Log of classified student questions
├── requirements.txt         # Python dependencies
├── templates/               # HTML templates for the Flask app
│   ├── base.html
│   ├── index.html
│   ├── dashboard.html
│   ├── attendance.html
│   └── question.html
├── static/                  # CSS and JS assets
│   ├── css/
│   └── js/
└── known_faces/             # Student face photos (gitignored — add locally)
```

---

## ⚙️ Installation

### 1. Clone the repository
```bash
git clone https://github.com/Joeee14/Smart-Classroom-Assistant.git
cd Smart-Classroom-Assistant
```

### 2. Create a virtual environment (recommended)
```bash
python -m venv venv
venv\Scripts\activate      # Windows
source venv/bin/activate   # macOS/Linux
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

> **Note:** `pyaudio` may require a separate installation on Windows:
> ```bash
> pip install pipwin
> pipwin install pyaudio
> ```

---

## 🚀 Usage

### ▶️ CLI Mode
```bash
python Project.py
```
Follow the on-screen prompts to:
1. Run an attendance session (webcam required)
2. Register unknown students
3. Start the Q&A phase (microphone required)

### 🌐 Web Dashboard Mode
```bash
python app.py
```
Then open [http://localhost:5000](http://localhost:5000) in your browser.

---

## 🖼️ Adding Student Faces

Place student photos inside the `known_faces/` directory following this naming convention:

```
known_faces/
├── 22100512_Youssef.jpg
├── 22100513_Ahmed.jpg
└── ...
```
Format: `<StudentID>_<Name>.jpg`

---

## 📊 Data Files

| File | Description |
|------|-------------|
| `attendance.csv` | Auto-generated; logs each session's attendance with mood |
| `student_questions.csv` | Auto-generated; logs classified Q&A entries |
| `training_data.csv` | Manual training data with `question,subject` columns |
| `topic_classifier.joblib` | Saved NLP model (auto-generated on first run) |

---

## 🛠️ Tech Stack

- **Python 3.10+**
- **OpenCV** — Camera capture & image processing
- **DeepFace** — Face recognition & emotion analysis
- **SpeechRecognition** — Audio input via Google Web Speech API
- **scikit-learn** — TF-IDF vectorization + Naive Bayes classification
- **Flask** — Web application framework
- **joblib** — Model persistence

---

## 📋 Requirements

- Python 3.10 or higher
- Webcam (for attendance / face registration)
- Microphone (for speech Q&A)
- Internet connection (for Google Speech API)

---

## 📄 License

This project was developed as part of the **CSE383 – Computer Vision** course at **AIU**.

---

## 👨‍💻 Author

**Youssef** — [@Joeee14](https://github.com/Joeee14)
