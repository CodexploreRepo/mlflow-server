FROM python:3.10-slim

LABEL maintainer="quannguyen"
LABEL organization="codexplore"

WORKDIR /app

ARG MLFLOW_VERSION

COPY requirements.txt requirements.txt

RUN apt-get update -y \
    && apt-get install -y iputils-ping libpq-dev gcc \
    && pip3 install --upgrade pip \    
    && pip3 install --no-cache-dir -r requirements.txt \
    && pip3 install --no-cache-dir mlflow==${MLFLOW_VERSION}

EXPOSE 5000
CMD mlflow server \
    --host 0.0.0.0 \
    --port 5000 \
    --default-artifact-root ${S3_BUCKET} \
    --backend-store-uri ${DB_BACKEND}
