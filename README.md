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

### 4. Train the Model

```
python train.py
```

### 5. Run the API Locally

```
uvicorn main:app --reload
```

### 6. Sample Input

Visit localhost:8000 and in the UI, provide below user input. And hit on Predict to see the result.

  "Pregnancies": 2,
  "Glucose": 130,
  "BloodPressure": 70,
  "BMI": 28.5,
  "Age": 45

<img width="1221" height="661" alt="image" src="https://github.com/user-attachments/assets/e7bcd525-a7e2-4ffc-9b18-8021f32e0979" />

### 7. Build the Docker Image

```
docker build -t mlops-diabetic-prediction .
```

### 8. Run the Container

```
docker run -p 8000:8000 mlops-diabetic-prediction
```

### 9. Deploy to Kubernetes

```
Use KIND or Minikube for this purpose.

kubectl apply -f mlops-diabetic-prediction-deployment.yaml
```

### 10. Test

```
kubectl port-forward svc/diabetes-prediction-service 9000:80
Forwarding from 127.0.0.1:9000 -> 8000
Forwarding from [::1]:9000 -> 8000
Handling connection for 9000
```

<img width="1189" height="658" alt="image" src="https://github.com/user-attachments/assets/d7475a97-89bc-47c5-9347-bd936624103c" />

<img width="1321" height="684" alt="image" src="https://github.com/user-attachments/assets/eab04341-0d1d-4787-b6a5-2a179394e504" />


## Tech Stacks
- FastAPI
- Docker
- Kubernetes (KinD or Minikube)
