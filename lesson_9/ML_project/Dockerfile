FROM python:3.8
LABEL maintainer="kondakov.yn@gmail.com"

WORKDIR "ML_in_business/lesson_9/ML_project/app"

COPY requirements.txt "ML_in_business/lesson_9/ML_project/requirements.txt"
RUN pip3 install -r requirements.txt

COPY . /opt/app
