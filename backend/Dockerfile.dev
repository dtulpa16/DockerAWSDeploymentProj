FROM python:alpine
#We will use Python as the base of our image

ENV PYTHONDONTWRITEBYTECODE=1
#This removes .pyc files from our container

ENV PYTHONBUFFERED=1
#Buffers the output so it looks "normal" to users within Docker

WORKDIR /app
ADD ./ ./
#This creates a working directory for our virtual environment,
#and copies the source code to that directory.

RUN python -m pip install --upgrade pip
RUN pip install -r requirements.txt
#This installs pip and all dependencies from the requirements.txt file

RUN adduser -u 5678 --disabled-password --gecos "" appuser && chown -R appuser /app
USER appuser
#This sets a default user for our application

EXPOSE 8000
#This will allow us to access our app using port 8000