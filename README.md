# End to End NLP_Text-Summarizer Project

    Author: Samarth R Bogar

## Steps to clone and run the project:

#### 1) Clone the respository

```bash
git clone https://github.com/Samarth-R/NLP_Text-Summarizer.git
```

#### 2) Create a conda environment after opening the project

```bash
conda create -n <env_name> python=3.8 -y
```

```bash
conda activate <env_name>
```

#### 3) Install the requirements and run app.py

```bash
pip install -r requirements.txt
```

```bash
python app.py
```

#### 4) Open local host and port in browser

```bash
# host='0.0.0.0' and port=5000 in this project (can be changed in app.py)
localhost:5000
```

## AWS-CICD-Deployment-with-Github-Actions

#### 1) Login to AWS Console

#### 2) Create IAM user for deployment

1.  Policies to be attached while creating user:

        1. AmazonEC2ContainerRegistryFullAccess
        2. AmazonEC2FullAccess

2.  Create and Download Access key as csv file for later use

#### 3) Create a ECR repository to push or store docker image

    Save the Repository URI for later use: 510670961706.dkr.ecr.ap-south-1.amazonaws.com/text-sum

#### 4) Create and EC2 instance - Ubuntu

#### 5) Connect to the EC2 instance and install docker

    sudo apt-get update -y

    sudo apt-get upgrade

    curl -fsSL https://get.docker.com -o get-docker.sh

    sudo sh get-docker.sh

    sudo usermod -aG docker ubuntu

    newgrp docker

#### 6) Configure EC2 as self-hosted runner through Github

    Do the following steps in your github:
    Settings > Actions > Runner > new self hosted runner > choose os > then run command one by one

#### 7) Setup github secrets

Open Settings > Secrets and variables > Actions > Add repository secrets one by one

    AWS_ACCESS_KEY_ID = copy from Access key csv file
    AWS_SECRET_ACCESS_KEY = copy from Access key csv file
    AWS_REGION = ap-south-1
    AWS_ECR_LOGIN_URI = demo>>  510670961706.dkr.ecr.ap-south-1.amazonaws.com
    ECR_REPOSITORY_NAME = text-sum

<!-- ## Workflows

1. Update config.yaml
2. Update params.yaml
3. Update entity
4. Update the configuration manager in src config
5. update the conponents
6. update the pipeline
7. update the main.py
8. update the app.py -->
