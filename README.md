# CardioGuard by Krushant Joshi - Cardiovascular Disease Risk Prediction

## Overview
CardioGuard is a Flask-based machine learning web app that predicts cardiovascular disease risk from 11 health inputs.
It uses a trained Random Forest model and provides instant prediction results through a modern multi-page interface.

## Project Identity
- Project Owner: **Krushant Joshi**
- Project Name: **CardioGuard by Krushant Joshi**

## Key Features
- ML-powered prediction API (`/predict` POST) using a trained `cardio_model.pkl`
- Multi-page web UI:
  - Home (`/`)
  - Dataset information (`/about`)
  - Model visuals (`/visuals`)
  - Pipeline explanation (`/model`)
  - Prediction form (`/predict`)
- Interactive prediction form with real-time modal result display
- Pre-generated model/data visualizations for fast rendering
- Responsive frontend with custom CSS animations and themed styling

## Tech Stack
- Frontend: HTML, CSS, Bootstrap 5, JavaScript (Fetch API)
- Backend: Python, Flask
- ML/Data: scikit-learn, pandas, numpy, joblib
- Visualization: matplotlib, seaborn
- Deployment: gunicorn (Render/Railway compatible)

## Project Structure
```text
ML-Project-main/
+-- app.py
+-- Procfile
+-- requirements.txt
+-- README.md
+-- model/
¦   +-- train_model.py
¦   +-- cardio_model.pkl
+-- static/
¦   +-- css/
¦   ¦   +-- style.css
¦   +-- js/
¦   ¦   +-- script.js
¦   +-- plots/
¦       +-- age_dist.png
¦       +-- confusion_matrix.png
¦       +-- feature_importance.png
¦       +-- learning_curve.png
¦       +-- prob_dist.png
¦       +-- roc_curve.png
+-- templates/
    +-- base.html
    +-- home.html
    +-- about.html
    +-- visuals.html
    +-- model_info.html
    +-- predict.html
```

## Local Setup
### 1. Install dependencies
```bash
pip install -r requirements.txt
```

### 2. Train model (if needed)
Run this if `model/cardio_model.pkl` is missing or you want a fresh model:
```bash
python model/train_model.py
```

### 3. Start app
```bash
python app.py
```
Open: `http://127.0.0.1:5000`

## Prediction Input Features
The model expects these 11 fields:
- `age`
- `gender`
- `height`
- `weight`
- `ap_hi`
- `ap_lo`
- `cholesterol`
- `gluc`
- `smoke`
- `alco`
- `active`

## Deployment (Render)
1. Push project to GitHub.
2. Create a new Web Service on Render.
3. Use:
- Build Command:
```bash
pip install -r requirements.txt && python model/train_model.py
```
- Start Command:
```bash
gunicorn app:app
```

## Notes
- This project is for educational purposes.
- Prediction output is not a substitute for professional medical diagnosis.