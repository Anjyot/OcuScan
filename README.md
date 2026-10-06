# OcuScan

OcuScan is an AI-powered vision screening platform designed to assess whether an individual likely requires spectacles based on eye images and optional symptom information. The system combines deep learning inference with a modern web interface to deliver a fast, accessible, and user-friendly evaluation experience.

## Overview

The platform analyzes ocular images using a computer vision model trained to identify patterns associated with refractive error. It classifies the input as either:

- Spectacles Required
- No Spectacles Needed

It also provides confidence scoring, prediction details, and a simple clinical summary to support decision-making in a screening workflow.

## Key Features

- AI-based classification for spectacle requirement detection
- Upload-based image analysis and webcam capture support
- FastAPI backend for model inference and system health endpoints
- React-based frontend with a responsive medical dashboard
- Confidence metrics and result summaries
- Modular architecture for model training, inference, and deployment

## Technology Stack

- Frontend: React, Vite, CSS
- Backend: Python, FastAPI, Uvicorn
- Deep Learning: PyTorch / Torchvision-based transfer learning model
- Image Processing: Pillow, NumPy
- Data Handling: Pandas

## System Architecture

```text
OcuScan/
├── backend/
│   ├── app.py
│   ├── model.py
│   ├── train.py
│   ├── generate_sample_data.py
│   ├── requirements.txt
│   ├── dataset/
│   └── saved_models/
├── frontend/
│   ├── src/
│   ├── package.json
│   ├── vite.config.js
│   └── index.html
├── README.md
└── .gitignore
```

## Project Workflow

1. User uploads an eye image or captures one via webcam.
2. The frontend sends the image to the backend API.
3. The inference service processes the image through the trained model.
4. The app returns the classification result, confidence level, and summary.

## Getting Started

### Prerequisites

- Python 3.10+
- Node.js 18+
- npm
- A compatible GPU is optional but recommended for faster training

### Backend Setup

```bash
cd backend

python -m venv venv
# Windows
.\venv\Scripts\activate
# macOS / Linux
# source venv/bin/activate

pip install -r requirements.txt
python app.py
```

The backend is available at:

- http://localhost:8000
- API documentation: http://localhost:8000/docs

### Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

The application is available at:

- http://localhost:5173

## Model and Training

The backend includes a deep learning pipeline for training and inference. Model development is organized around a transfer learning approach to support rapid, reliable classification from ocular imagery.

Training can be executed with the backend training utility and requires a compatible dataset in the expected layout. Place training data under `backend/dataset/` and trained model artifacts under `backend/saved_models/` on your local machine. These directories are intentionally excluded from version control to avoid distributing ocular images or derived model files. Use only datasets you are authorized to process and share.

## API Overview

The backend exposes endpoints for system status and inference, including:

- GET /status
- GET /api/status
- POST /predict
- POST /api/predict
- GET /datasets

These endpoints support both file uploads and base64 image payloads.

## Use Cases

- Educational vision screening demonstrations
- AI-assisted preliminary eye assessment workflows
- Research and prototype evaluation in ophthalmic screening
- Frontend-backend integration for intelligent image classification systems

## Benefits

- Fast and accessible screening flow
- Modern web interface for user interaction
- Clear output for prediction and confidence
- Easy extension for additional screening models or datasets

## License

This project is for educational and research purposes. Please review and comply with the applicable licensing terms for any datasets, libraries, or assets used in the project.

## Contact

For questions or collaboration inquiries, please reach out through the project repository or the relevant contact channel associated with the project owner.
