FROM python:3.9-slim

WORKDIR /app

RUN apt-get update && apt-get install -y \
    build-essential \
    curl \
    software-properties-common \
    git \
    && rm -rf /var/lib/apt/lists/* 

RUN apt-get update && apt-get install -y python3-opencv
RUN pip install opencv-python

COPY . .
RUN pip install --upgrade pip && pip install -r requirements.txt

EXPOSE 8080

ENTRYPOINT streamlit run web.py --server.address=0.0.0.0 --server.port=8080
