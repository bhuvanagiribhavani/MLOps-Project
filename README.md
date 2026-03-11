# Diabetes Prediction System

An end-to-end MLOps project that predicts whether a person is diabetic based on health metrics, using **FastAPI**, **Docker**, and **Kubernetes**.

---

## Project Structure

```
MLOps-Project/
├── app/
│   ├── __init__.py
│   ├── main.py              # FastAPI application
│   ├── train.py              # Model training script
│   └── diabetes_model.pkl    # Trained model
├── frontend/
│   └── index.html            # Web UI
├── k8s/
│   └── k8s-deploy.yml        # Kubernetes manifests
├── Dockerfile
├── requirements.txt
├── README.md
├── LICENSE
└── .gitignore
```

---

## Problem Statement

Predict if a person is diabetic based on:

- Pregnancies
- Glucose
- Blood Pressure
- BMI
- Age

Uses a **Random Forest Classifier** trained on the [Pima Indians Diabetes Dataset](https://raw.githubusercontent.com/plotly/datasets/master/diabetes.csv).

---

## Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/BhuvanagiriBhavani/MLOps-Project.git
cd MLOps-Project
```

### 2. Create a Virtual Environment

```bash
python -m venv .mlops
.mlops\Scripts\activate      # Windows
# source .mlops/bin/activate  # macOS / Linux
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Train the Model

```bash
python app/train.py
```

### 5. Run the API Locally

```bash
uvicorn app.main:app --reload
```

The API will be available at `http://127.0.0.1:8000`.

### 6. Open the Web UI

Open `frontend/index.html` in a browser and submit predictions through the form.

---

## API Usage

**POST** `/predict`

```json
{
  "Pregnancies": 2,
  "Glucose": 130,
  "BloodPressure": 70,
  "BMI": 28.5,
  "Age": 45
}
```

**Response:**

```json
{
  "diabetic": true
}
```

---

## Docker

### Build

```bash
docker build -t diabetes-prediction-model .
```

### Run

```bash
docker run -p 8000:8000 diabetes-prediction-model
```

---

## Kubernetes

```bash
kubectl apply -f k8s/k8s-deploy.yml
```

Access via the LoadBalancer service on port 80.

---

## Tech Stack

- **Python** - scikit-learn, pandas, joblib
- **FastAPI** - REST API
- **Docker** - Containerization
- **Kubernetes** - Orchestration
- **HTML/CSS/JS** - Frontend

---

## Author

**BhuvanagiriBhavani**

---

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.



