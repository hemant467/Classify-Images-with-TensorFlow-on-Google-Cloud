# Classify Images 🖼️ with TensorFlow on Google Cloud 
End-to-end machine learning 🤖 workflow on Google Cloud Vertex AI ֎. Includes training a CNN for image classification with a custom Python script 📜, running training via Vertex AI 💠 Custom Jobs, deploying the model 🤖 to an online prediction endpoint, and sending prediction requests 📜 to validate deployment 🛠️.

# Overview :

This repository demonstrates an end-to-end machine learning workflow on Google Cloud Vertex AI 💠. It covers training a Convolutional Neural Network (CNN) for image classification, deploying the trained model 🤖 to an online prediction endpoint, and performing predictions to validate the deployment 🛠️.

The project 📜 highlights practical experience with model 🤖 training, deployment 🛠️, and serving at scale using modern cloud ML infrastructure 🏗️.

# Features ✨ :

✅ Custom Python script for CNN model training

✅ Training execution using Vertex AI Custom Training Jobs

✅ Model artifact saving for reproducibility

✅ Deployment to Vertex AI Online Prediction Endpoint

✅ Sending online prediction requests and validating responses

✅ End-to-end automation for ML workflow on GCP

# Architecture 🏗️ :

```text
    Dataset
        ↓
CNN Training Script
        ↓
Vertex AI Custom Job
        ↓
 Trained Model
        ↓
Online Prediction Endpoint
        ↓
    Predictions
```

# Prerequisites 📝 :

- Google Cloud account with Vertex AI enabled
- Python 3.8+ environment
- Required Python packages (install via pip install -r requirements.txt)
- GCP project with sufficient permissions for AI Platform and storage

# Usage :
1. Train the CNN Model
```
python train_cnn.py --data-dir <DATA_PATH> --model-dir <MODEL_PATH>
```

2. Run Training on Vertex AI 🤖 
```
gcloud ai custom-jobs create \
    --region=<REGION> \
    --display-name=<JOB_NAME> \
    --python-package-uris=<PACKAGE_URI> \
    --module-name=train_cnn \
    --job-dir=<MODEL_PATH>
```

3. Deploy Model to Online Endpoint 🛠️
```
gcloud ai endpoints create --region=<REGION> --display-name=<ENDPOINT_NAME>
gcloud ai endpoints deploy-model <ENDPOINT_ID> \
    --model=<MODEL_ID> \
    --machine-type="n1-standard-4"
```

4. Send Online Prediction Request 📜 
```
from google.cloud import aiplatform

endpoint = aiplatform.Endpoint("<ENDPOINT_ID>")
response = endpoint.predict(instances=[<YOUR_INPUT>])
print(response)
```

# Repository Structure 🏗️ :
```bash
├── train_cnn.py          # CNN training script
├── requirements.txt      # Python dependencies
├── README.md             # Project documentation
├── notebooks/            # Optional Jupyter notebooks for experiments
├── scripts/              # Deployment & utility scripts
└── data/                 # Sample datasets
```

## Outcomes 💯 :

By working through this project, you will:

- Gain hands-on experience with Vertex AI 💠 Custom Jobs

- Understand end-to-end ML model 🤖 lifecycle in cloud environments

- Learn model deployment 🛠️ and online prediction techniques

- Develop skills in troubleshooting and automating ML 🤖 workflows

<img src="https://readme-typing-svg.herokuapp.com/?lines=🤖+CNN+Image+Classification+on+Vertex+AI+💠;End-to-End+ML+Workflow+on+Google+Cloud;Train,+Deploy+and+Predict+Seamlessly+📊&font=Fira%20Code&color=%23FFD700&center=true&width=520&height=50">
