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
3. export the credentials in AWS CLI by runing 'aws configure'(in bash shell)
4. create a s3 bucket(all the artifacts from mlflow save inside s3 bucket)
5. create EC2 machine-ubuntu & add security groups 5000 port

Run below commands on EC2 machine-ubuntu
```bash
sudo apt update

sudo apt install python3-pip

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
mlflow server -h 0.0.0.0 --default-artifact-root s3://mlflowaws-buck
#run above and go to instance open address public DNS, add 5000 port into url and make sure https to http. then MLFlow UI will open.

# open public IPv4 DNS to the port 5000

##set uri in local terminal and code. after open mlflow ui from instance address, copy the address and update here
#export local bash terminal below code.
export MLFLOW_TRACKING_URI=http://ec2-16-171-19-114.eu-north-1.compute.amazonaws.com:5000/
```

#update tracking uri in the code. then run python file in bash.
#you can share tracking uri with anyone.