# GAIT AI — Vision-Based Computational Biomechanics Platform

## Overview

GAIT AI is a real-time computational biomechanics platform designed to analyze human gait using computer vision, pose estimation, biomechanical signal processing, and AI-assisted analytical reasoning.

The platform captures lower-limb motion through a monocular camera, extracts pose landmarks using MediaPipe Pose, computes gait-related biomechanical metrics, and generates analytical mobility reports through deterministic reasoning and optional LLM-assisted interpretation.

The system is intended for:

- Biomechanics research
- Gait analytics
- Mobility monitoring
- Rehabilitation support
- Educational demonstrations
- Computational healthcare exploration
- AI-assisted movement analysis

---

# Key Features

## Real-Time Pose Tracking

- MediaPipe Pose-based lower-body tracking
- Runtime skeletal visualization
- Real-time landmark acquisition
- Live gait computation

---

## Biomechanical Analysis

The system computes:

- Knee angle
- Cadence
- Gait variability
- Walking speed
- Range of motion (ROM)
- Temporal gait metrics

---

## Analytical Intelligence Layer

- Deterministic biomechanics reasoning engine
- Normative gait comparison
- Mobility interpretation
- Stability assessment
- Gait quality evaluation

---

## AI-Assisted Reporting

Optional Google Gemini integration enables:

- Technical gait summaries
- Biomechanical interpretation
- AI-generated analytical reports
- Mobility insights

---

## Full Stack Architecture

- Flask backend API
- React frontend dashboard
- Tailwind UI
- CSV-based session logging
- Modular backend design

---

# System Architecture

```text
Camera Input
      ↓
MediaPipe Pose Runtime
      ↓
Landmark Acquisition
      ↓
Biomechanical Processing
      ↓
Gait Metric Extraction
      ↓
Reasoning Engine
      ↓
Session Analyzer
      ↓
Flask API
      ↓
React Dashboard
```
---

 # Project Structure

 ```text
GAIT_AI/

├── backend/
│
│   ├── acquisition/
│   │   └── pose_runtime.py
│   │
│   ├── analysis/
│   │   └── session_analyzer.py
│   │
│   ├── biomechanics/
│   │   └── kinematics.py
│   │
│   ├── calibration/
│   │   └── calibrator.py
│   │
│   ├── gait/
│   │   ├── cadence_engine.py
│   │   └── cycle_detector.py
│   │
│   ├── intelligence/
│   │   ├── reasoning_engine.py
│   │   └── gemini_reporter.py
│   │
│   ├── processing/
│   │   ├── smoothers.py
│   │   └── validators.py
│   │
│   ├── storage/
│   │   └── csv_logger.py
│   │
│   ├── utils/
│   │
│   ├── data/
│   │   └── session_logs/
│   │
│   ├── app.py
│   ├── main.py
│   └── .env
│
├── frontend/
│
│   ├── src/
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── GaitDashboard.jsx
│   │
│   ├── tailwind.config.js
│   ├── postcss.config.js
│   └── package.json
│
├── venv/
│
└── README.md
```
---

# Technologies Used

## Backend

- Python 3.11
- Flask
- Flask-CORS
- NumPy
- Pandas
- OpenCV
- MediaPipe

---

## Frontend

- React
- Vite
- Tailwind CSS

---

## AI Integration

- Google Gemini API

---

# Biomechanical Parameters

| Parameter | Description |
|---|---|
| Cadence | Number of steps per minute |
| Knee ROM | Knee range of motion during gait |
| Gait Variability | Temporal inconsistency between gait cycles |
| Walking Speed | Estimated locomotion speed |
| Confidence Score | Pose estimation reliability |

---

# Normative Biomechanics Logic

The platform compares observed gait metrics against approximate normative adult walking ranges derived from biomechanics literature.

Example interpretations include:

- Reduced cadence
- Elevated gait variability
- Reduced knee excursion
- Altered gait rhythm
- Mobility instability

These observations are used for:
- gait characterization,
- movement analysis,
- and biomechanical interpretation.

---

# Installation Guide

# 1. Clone Repository

```bash
git clone <repository_url>
cd gait_ai
```

---

# 2. Create Virtual Environment

```bash
python -m venv venv
```

---

# 3. Activate Environment

## Windows

```bash
venv\Scripts\activate
```

## Linux / macOS

```bash
source venv/bin/activate
```

---

# 4. Install Backend Dependencies

```bash
pip install flask flask-cors numpy pandas mediapipe opencv-python python-dotenv google-genai
```

---

# 5. Frontend Setup

Navigate to frontend:

```bash
cd frontend
```

Install frontend dependencies:

```bash
npm install
```

Install Tailwind CSS:

```bash
npm install -D tailwindcss@3 postcss autoprefixer
```

Initialize Tailwind:

```bash
npx tailwindcss init -p
```

---

# 6. Configure Tailwind

## `frontend/tailwind.config.js`

```javascript
/** @type {import('tailwindcss').Config} */

export default {

  content: [

    "./index.html",

    "./src/**/*.{js,ts,jsx,tsx}",
  ],

  theme: {

    extend: {},
  },

  plugins: [],
}
```

---

# 7. Configure CSS

## `frontend/src/index.css`

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

---

# Environment Variables

Create:

```text
backend/.env
```

Add:

```env
GEMINI_API_KEY=your_api_key_here
```

---

# Running the Backend

Navigate to backend:

```bash
cd backend
```

Run Flask API:

```bash
python app.py
```

Expected:

```text
Running on http://127.0.0.1:5000
```

---

# Running the Frontend

Open second terminal:

```bash
cd frontend
npm run dev
```

Expected:

```text
Local: http://localhost:5173
```

---

# Running Real-Time Gait Acquisition

Inside backend:

```bash
python main.py
```

This launches:

- MediaPipe runtime
- Pose tracking
- Knee-angle computation
- Cadence estimation
- Real-time visualization
- CSV session logging

---

# Session Analysis

Analyze latest gait session:

```bash
python -m analysis.session_analyzer
```

This generates:

- Biomechanical metrics
- Technical gait analysis
- Mobility interpretation
- AI-assisted report summary

---

# Flask API Endpoint

## Get Latest Report

```http
GET /api/report
```

Example response:

```json
{
  "mean_cadence": 18.2,
  "knee_rom": 31.4,
  "gait_interval_cv": 42.1,
  "walking_speed": 1.1,
  "summary": "Observed cadence is below normative adult walking ranges.",
  "technical_summary": "Detailed biomechanical interpretation..."
}
```

---

# Frontend Dashboard Features

The React dashboard displays:

- Session summary
- Cadence analysis
- Knee ROM
- Gait variability
- Walking speed
- Confidence metrics
- Technical gait report
- Status indicators

---

# Example Analytical Output

The platform generates analytical gait interpretations such as:

```text
1. Summary of Biomechanical Performance

The gait analysis session reveals an altered locomotion pattern characterized by several deviations from normative ranges.

Mean cadence was observed below typical adult walking ranges. Knee range of motion was reduced relative to functional gait expectations. Elevated gait interval variability indicates temporal instability and reduced rhythmic consistency during walking.

2. Observations on Gait Stability

Elevated gait variability may indicate reduced temporal consistency in gait rhythm and possible balance-control inefficiencies.

3. Mobility Insights

Reduced knee range of motion may affect propulsion, shock absorption, and gait efficiency.

4. Clinical Interpretation Disclaimer

This framework is intended for biomechanics analysis and research support only. It is not a standalone diagnostic system.
```

---

# Backend API Flow

```text
CSV Session Data
        ↓
Session Analyzer
        ↓
Reasoning Engine
        ↓
Gemini Reporter
        ↓
Flask API
        ↓
React Dashboard
```

---

# Frontend Dashboard Layout

The frontend includes:

- Session Summary Panel
- Biomechanical Score Cards
- Cadence Visualization
- Knee ROM Metrics
- Gait Variability Indicators
- Walking Speed Indicators
- Confidence Metrics
- Technical Analytical Report
- Backend Error Handling
- Loading States

---

# AI-Assisted Reporting

The platform optionally integrates with the Google Gemini API to generate:

- Descriptive gait interpretation
- Technical mobility analysis
- Biomechanical summaries
- AI-generated analytical reports

Fallback deterministic summaries are used if the API is unavailable.

---

# Current Limitations

- Monocular camera estimation only
- Approximate walking-speed estimation
- Single-person tracking
- Limited clinical validation
- Indoor testing primarily performed
- Pose quality dependent on visibility

---

# Future Improvements

- Bilateral gait analysis
- Left-right asymmetry metrics
- Live dashboard streaming
- PDF report export
- Historical session comparison
- Multi-camera support
- Advanced gait phase segmentation
- Deep learning anomaly detection
- Clinical-grade calibration
- Real-time WebSocket streaming
- Cloud deployment
- Session database integration

---

# Research and Educational Value

This project demonstrates:

- Applied biomechanics
- Computer vision
- Pose estimation
- Human motion analytics
- AI-assisted reasoning
- Full-stack healthcare technology development

The platform can serve as:

- Research prototype
- Academic demonstration
- Hackathon project
- Educational biomechanics system
- Computational mobility analytics framework

---

# Clinical Disclaimer

This system is intended solely for:

- biomechanics research,
- educational use,
- and mobility-analysis support.

It is NOT:

- a medical device,
- a clinical diagnostic platform,
- or a substitute for professional healthcare evaluation.

Any medical interpretation should be performed only by qualified healthcare professionals.

---

# License

This project is intended for academic, research, and educational purposes.

---

# Author

Developed as a computational biomechanics and gait analytics platform integrating:

- Computer vision
- Biomechanical intelligence
- AI-assisted analytical reasoning
- Full-stack visualization systems