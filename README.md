# mlflow server

- This is to setup mlflow server on AWS

<p align="center"><img src='./assets/img/mlflow-architecture.webp' /></p>

- `boto3` is to connect with S3

```shell
python3 -m venv venv
pip install --upgrade pip

mlflow server --default-artifact-root s3://upskills-landing-zone/mlflow/ --backend-store-uri postgresql://root:root@db:5432/mlflow
```

- To access mlflow server: http://localhost:8080/
