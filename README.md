# Project: Fake Image Detection

The objective of this project is to develop a service capable of determining whether an image is fake or genuine.

## Approach:
A dual-stream architecture was chosen for the task:

1. **Stream 1 - Feature Extraction via Convolutional Neural Networks (CNN):**  
   This stream processes the image to extract general features and patterns, which are indicative of authenticity or forgery.

2. **Stream 2 - Noise Detection Using the Laplacian Filter:**  
   In this stream, a Laplacian filter is applied to isolate noise in the image. This step helps identify anomalies that could indicate forgery, such as inconsistencies introduced during manipulation.

## Integration and Classification:
The outputs from the two streams are combined and passed through an attention layer. The attention mechanism searches for contextual relationships within the image to enhance the detection capability. Finally, the processed data is classified to determine if the image is fake or genuine.

---

## Repository Structure

The project is organized into multiple branches to manage development and deployment effectively:

- **`main`:**  
  The primary branch for production-ready code. All updates from development branches are merged here after successful testing.

- **`train`:**  
  This branch focuses on the development of the fake image detection model. It includes:  
  - Model architecture (dual-stream + attention).  
  - Training and evaluation scripts.  
  - Preprocessing and data augmentation logic.

- **`serv`:**  
  This branch is dedicated to developing the service for deploying the model. It includes:  
  - API endpoints for inference.  
  - Integration of the trained model with the service.  
  - Docker configurations for containerized deployment.

---
