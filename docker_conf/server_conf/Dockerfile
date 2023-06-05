FROM python:3.10.11-slim

RUN apt update && apt -y upgrade

WORKDIR /app

COPY requirements.txt /app/requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

COPY ./server_src /app
EXPOSE 5000