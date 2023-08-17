FROM python:3.10-slim-buster

WORKDIR /app

COPY requirements.txt requirements.txt
RUN apt-get update \
    && apt-get -y install libpq-dev gcc \
    && pip3 install --upgrade pip \    
    && pip3 install --no-cache-dir -r requirements.txt

EXPOSE 5000
CMD mlflow server \
    --host 0.0.0.0 \
    --port 5000 \
    --default-artifact-root ${S3_BUCKET} \
    --backend-store-uri ${DB_BACKEND}
