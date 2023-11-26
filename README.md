# MLFlow-with-AWS-Dagshub-Local

## Dagshub API:
(go to Dagshub & connect github repo, copy credentials from remote button)

MLFLOW_TRACKING_URI=https://dagshub.com/Kasun-Tharaka/MLFlow-with-AWS-Dagshub-Local.mlflow \
MLFLOW_TRACKING_USERNAME=Kasun-Tharaka \
MLFLOW_TRACKING_PASSWORD=e14b42621271f1b9a83c6e90bd40a2d2ab1929da \
python script.py


```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/Kasun-Tharaka/MLFlow-with-AWS-Dagshub-Local.mlflow

export MLFLOW_TRACKING_USERNAME=Kasun-Tharaka

export MLFLOW_TRACKING_PASSWORD=e14b42621271f1b9a83c6e90bd40a2d2ab1929da

```
run above three commands in terminal one by one

Dagshub is public domain, anyone can see your experiments. if you want to keep it private go for AWS


# MlFlow AWS
## MlFlow AWS setup
1. login to AWS consol
2. create IAM user with AdministratorAccess
3. export the credentials in AWS CLI by runing 'aws configure'
4. create a s3 bucket
5. create EC2 machine-ubuntu & add security groups 5000 port

Run below commands on EC2 machine-ubuntu
```bash
sudo apt update

sudu apt install python3-pip

sudo pip3 install pipenv

sudo pip3 install virtualenv

mkdir mlflow

cd mlflow

pipenv install mlflow

pipenv install awscli

pipenv install boto3

pipenv shell

## set aws credentials
aws configure

## Finally
mlflow server -h 0.0.0.0 --default-artifact-root s3://mlflow-test-23

# open public IPv4 DNS to the port 5000

##set uri in local terminal and code
export MLFLOW_TRACKING_URI=
```