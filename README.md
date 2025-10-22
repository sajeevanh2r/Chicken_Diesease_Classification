
# 🐔 Chicken Disease Classification – Project

This project implements an **end-to-end Deep Learning pipeline** for classifying chicken diseases using **MLOps practices**.  
It uses **DVC** for experiment tracking, **Docker** for containerization, **GitHub Actions** for CI/CD automation, and **AWS (EC2, IAM, ECR)** for cloud deployment.

---

## 🚀 Project Workflow

1. **Update `config.yaml`** – Configure paths, model settings, and directories.  
2. **Update `secrets.yaml` [Optional]** – Add sensitive information if necessary.  
3. **Update `params.yaml`** – Adjust hyperparameters and model configurations.  
4. **Update entity classes** – Define and modify project entities.  
5. **Update configuration manager (`src/config`)** – Manage YAML and project settings.  
6. **Update components** – Implement logic for data ingestion, model training, and evaluation.  
7. **Update pipeline** – Integrate all modules for a smooth workflow.  
8. **Update `main.py`** – Run and manage the complete training process.  
9. **Update `dvc.yaml`** – Automate and track pipeline stages using DVC.

---

## ⚙️ How to Run

### **Step 1:** Clone the Repository

```bash
git clone https://github.com/sajeevanh2r/Chicken_Diesease_Classification.git
cd Chicken_Diesease_Classification
````

### **Step 2:** Create and Activate Conda Environment

```bash
conda create -n cnncls python=3.8 -y
conda activate cnncls
```

### **Step 3:** Install Dependencies

```bash
pip install -r requirements.txt
```

### **Step 4:** Run the Application

```bash
python app.py
```

Then open your browser at:

```
http://127.0.0.1:5000/
```

or

```
http://0.0.0.0:80/
```

---

## 🧩 DVC Commands

```bash
dvc init
dvc repro
dvc dag
```

**Command Descriptions:**

* `dvc init` → Initialize DVC in the project
* `dvc repro` → Reproduce the pipeline based on dependencies
* `dvc dag` → Visualize the pipeline graph

---

## 🐳 Docker Setup

### **Step 1:** Build the Docker Image

```bash
docker build -t chicken-disease-classification .
```

### **Step 2:** Run the Docker Container

```bash
docker run -p 8080:8080 chicken-disease-classification
```

Now open in your browser:

```
http://localhost:8080
```

---

### **Step 3:** (Optional) Push to AWS ECR

```bash
# Authenticate Docker with AWS
aws ecr get-login-password --region <your-region> | docker login --username AWS --password-stdin <aws-account-id>.dkr.ecr.<your-region>.amazonaws.com

# Tag the image
docker tag chicken-disease-classification:latest <aws-account-id>.dkr.ecr.<your-region>.amazonaws.com/chicken-disease-classification:latest

# Push the image to ECR
docker push <aws-account-id>.dkr.ecr.<your-region>.amazonaws.com/chicken-disease-classification:latest
```

---

### **Step 4:** Deploy on AWS EC2

1. Launch an **EC2 instance**.
2. Install **Docker** on the instance.
3. Pull the image from **ECR**.
4. Run the container (make sure to expose port 8080 or 80).

---

## ⚡ GitHub Actions – CI/CD Pipeline

This project includes a **GitHub Actions** workflow for automation:

* Automatically **builds and tests** your project.
* **Deploys** Docker images to **AWS ECR/EC2** when changes are pushed to the `main` branch.
* Ensures **Continuous Integration and Continuous Delivery (CI/CD)**.

---

## 🧠 Tech Stack

* **Python 3.8+**
* **TensorFlow / Keras**
* **Flask**
* **DVC (Data Version Control)**
* **Docker**
* **GitHub Actions**
* **AWS (EC2, IAM, ECR)**

---

## 📊 Results & Deployment Architecture

This section explains the **end-to-end workflow and deployment** of the Chicken Disease Classification project. Screenshots and diagrams can be added under each heading to illustrate the setup.

---

### **1. IAM (AWS Identity and Access Management)**

*Description:*  
IAM is used to create users, roles, and permissions for securely accessing AWS services (EC2, ECR, etc.).  

*Add image here:*  
![IAM Scre<img width="1915" height="853" alt="iam user -aws1" src="https://github.com/user-attachments/assets/a1c99cfc-dc1e-457d-86de-823b991e1a6a" />
enshot](path_to_iam_image.png)

---

### **2. EC2 (Elastic Compute Cloud)**

*Description:*  
EC2 hosts the Docker container running the Flask app for inference. It provides scalable compute resources for model deployment.  

*Add image here:*  
![EC2 Screenshot](path_to_ec2_image.png)

---

### **3. ECR (Elastic Container Registry)**

*Description:*  
ECR stores Docker images of the project. It integrates with CI/CD pipelines for automated deployment.  

*Add image here:*  
![ECR Screenshot](path_to_ecr_image.png)

---

### **4. CI/CD (GitHub Actions)**

*Description:*  
GitHub Actions automates the pipeline:  
- Builds the Docker image  
- Pushes to ECR  
- Deploys on EC2 automatically  

*Add image here:*  
![CI/CD Screenshot](path_to_cicd_image.png)

---

### **5. Deployment on AWS**

*Description:*  
Step-by-step deployment:  
1. Build Docker image locally  
2. Push to ECR  
3. Pull image on EC2  
4. Run container to serve Flask API  

*Add image here:*  
![Deployment Screenshot](path_to_deployment_image.png)

---

### **6. DVC DAG**

*Description:*  
Shows the pipeline stages managed by DVC (data ingestion, training, evaluation, model artifacts).  

*Add image here:*  
![DVC DAG Screenshot](path_to_dvc_dag_image.png)

---

### **7. AWS to GitHub Connection**

*Description:*  
Illustrates integration between GitHub Actions and AWS for automated deployment.  

*Add image here:*  
![GitHub-AWS Connection Screenshot](path_to_github_aws_image.png)

---

### **8. Model Deployment Results**

*Description:*  
- Model predictions on sample images  
- Accuracy metrics, loss graphs, or any evaluation results  
- Screenshot of Flask app running with prediction results  

*Add image here:*  
![Model Deployment Results Screenshot](path_to_results_image.png)

---


## 👨‍💻 Author

**Radhakrishnan Sajeevan**
BSc (Hons) in Management Information Systems – NSBM Green University
GitHub: [@sajeevanh2r](https://github.com/sajeevanh2r)

---

## 📜 License

This project is licensed under the **MIT License** – you’re free to use, modify, and distribute it with attribution.

---

## 💡 Acknowledgements

Special thanks to all open-source contributors and MLOps resources that helped in building this project.

---

```

Would you like me to now **append a ready-to-use `Dockerfile` (for Flask + TensorFlow + DVC)** section at the bottom of this README so it’s fully production-ready for deployment on AWS or locally?
```
