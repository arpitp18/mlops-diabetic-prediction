# Diabetes Prediction Model

This project is for  **Building and Deploying an ML Model** using a simple and real-world use case: predicting whether a person is diabetic based on health metrics.
Project consists of:

- Model Training
- Building the Model locally
- API Deployment with FastAPI
- Dockerization
- Kubernetes Deployment

---

## What it does?

Predict if a person is diabetic based on:
- Pregnancies
- Glucose
- Blood Pressure
- BMI
- Age

---

## steps:

### 1. Clone the Repo

### 2. Create Virtual Environment

```
python3 -m venv .mlops
source .mlops/bin/activate
```

### 3. Install Dependencies

```
pip install -r requirements.txt
```

### Train the Model

```
python train.py
```

### Run the API Locally

```
uvicorn main:app --reload
```

### Sample Input

Visit localhost:8000 and in the UI, provide below user input. And hit on Predict to see the result.

  "Pregnancies": 2,
  "Glucose": 130,
  "BloodPressure": 70,
  "BMI": 28.5,
  "Age": 45

<img width="1221" height="661" alt="image" src="https://github.com/user-attachments/assets/e7bcd525-a7e2-4ffc-9b18-8021f32e0979" />

### Build the Docker Image

```
docker build -t mlops-diabetic-prediction .
```

### Run the Container

```
docker run -p 8000:8000 mlops-diabetic-prediction
```

### Deploy to Kubernetes

```
Use KIND or Minikube for this purpose.

kubectl apply -f mlops-diabetic-prediction-deployment.yaml
```
## Tech Stacks
- FastAPI
- Docker
- Kubernetes (KinD or Minikube)
