# mlflow server

- This is to setup mlflow server on AWS

<p align="center"><img src='./assets/img/mlflow-architecture.webp' /></p>

- `boto3` is to connect with S3

```
python3 -m venv venv
pip install --upgrade pip

mlflow server --default-artifact-root s3://upskills-landing-zone/mlflow/ --backend-store-uri postgresql://root:root@localhost:8080/mlflow

```
