# 🏥 Medical AI Chatbot (End-to-End RAG Application).
This repository features a career-boosting project focused on building a scalable, professional Medical AI Chatbot. Utilizing a custom medical dataset and Retrieval-Augmented Generation (RAG).

<img width="1000" height="527" alt="image" src="https://github.com/user-attachments/assets/f724adfd-3909-4df3-84ff-d2acc2d74fdd" />

## Key Features
- Advanced AI Architecture: Master the creation of a chatbot using Python, custom medical data, and Large Language Models (LLMs).

- Semantic Search: Implementation of high-performance semantic search using Pinecone vector databases and vector embeddings.

- Web Framework: A user-friendly web interface built with Flask to handle real-time medical queries.

- Deployment: Step-by-step masterclass on deploying applications using AWS, Docker, and automated CI/CD pipelines.

- Scalable Design: Best practices for creating a modular, scalable architecture suitable for professional portfolios.

<img width="800" height="421" alt="image" src="https://github.com/user-attachments/assets/4049872e-672c-48b6-8e61-8328cedf295f" />


# How to run on localhost?
### STEPS:

Clone the repository

```bash
Project repo: https://github.com/Cheetah-lhp/End-to-end-Medical-Chatbot-Generative-AI.git
```

### STEP 01 - Create a conda enviroment after opening the repository

```bash
conda create -n medibot python=3.10 -y
```

```bash
conda activate medibot
```

### STEP 02 - install the requirements
```bash
pip install -r requirement.txt
```

### Create a .env file in the root directory and add your Pinecone & openai credentials as follows:
```ini
PINECONE_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
OPENAI_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

```bash
# run the following command to store embeddings to pinecone
python store_index.py
```

```bash
# Finally run the following command
python app.py
```
Now,
```bash
open up web browser: localhost:8080
```

### Techstack Used:
- Python
- LangChain
- Flask
- Gemini
- PineCone

# AWS CICD-Deployment with Github-Actions

## 1. Login to AWS console

## 2. Create IAM user for deployment

    #with specific access

    1. EC2 access: It is virtual machine
    
    2. ECR: Elastic Container Registry to save your docker image in AWS


    #Description: About the deployment

    1. Build docker image of the source code

    2. Push your docker image to ECR

    3. Launch your EC2

    4. Pull your image from ECR in EC2

    5. Launch your docker image in EC2

    #Policy:

    1. AmazonEC2ContainerRegistryFullAccess

    2. AmazonEC2FullAccess

## 3. Create ECR repo to store/save docker image
    - Save the URI: 

## 4. Create EC2 machine (Ubuntu)

## 5. Open EC2 and Install docker in EC2 Machine:

    #optinal

    sudo apt-get update -y

    sudo apt-get upgrade

    #required

    curl -fsSL https://get.docker.com -o get-docker.sh

    sudo sh get-docker.sh

    sudo usermod -aG docker ubuntu

    newgrp docker

## 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one

## 7. Setup github secrets:

- AWS_ACCESS_KEY_ID
- AWS_SECRET_ACCESS_KEY
- AWS_DEFAULT_REGION
- ECR_REPO
- PINECONE_API_KEY
- OPENAI_API_KEY
  
Reference: https://www.youtube.com/watch?v=CXKMfYX62_8&t=3999s
