# Docker Flask App

## Project Overview

This project demonstrates the fundamentals of Docker by containerizing a simple Flask web application.

The application returns a simple message when accessed through a web browser and is packaged into a Docker image that can be run on any machine with Docker installed.

---

## Technologies Used

* Python 3.12
* Flask
* Docker
* Docker Hub

---

## Project Structure

```text
docker-flask-app/
│
├── app.py
├── Dockerfile
└── README.md
```

---

## Flask Application

### app.py

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Hello from Docker DevOps Project - Version 2"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

---

## Dockerfile

```dockerfile
FROM python:3.12-slim

WORKDIR /app

COPY . .

RUN pip install flask

EXPOSE 5000

CMD ["python", "app.py"]
```

---

## Build Docker Image

```bash
docker build -t flask-app:v1 .
```

Build Version 2:

```bash
docker build -t flask-app:v2 .
```

---

## Verify Images

```bash
docker images
```

Example Output:

```text
REPOSITORY   TAG
flask-app    v1
flask-app    v2
```

---

## Run Container

```bash
docker run -p 5000:5000 flask-app:v1
```

Access application:

```text
http://localhost:5000
```

---

## Docker Image Versioning

Docker tags are used for version control.

Examples:

```text
flask-app:v1
flask-app:v2
flask-app:latest
```

Benefits:

* Version tracking
* Easy rollback
* Controlled deployments

---

## Docker Hub

### Login

```bash
docker login
```

### Tag Image

```bash
docker tag flask-app:v2 <dockerhub-username>/flask-app:v1
```

Example:

```bash
docker tag flask-app:v2 john/flask-app:v1
```

### Push Image

```bash
docker push <dockerhub-username>/flask-app:v1
```

Example:

```bash
docker push john/flask-app:v1
```

---

## Pull Image from Docker Hub

```bash
docker pull <dockerhub-username>/flask-app:v1
```

---

## Run Pulled Image

```bash
docker run -p 5002:5000 <dockerhub-username>/flask-app:v1
```

Access application:

```text
http://localhost:5002
```

---

## Docker Workflow

```text
Application Code
       ↓
Dockerfile
       ↓
docker build
       ↓
Docker Image
       ↓
docker push
       ↓
Docker Hub
       ↓
docker pull
       ↓
docker run
       ↓
Container
```

---

## Skills Demonstrated

* Flask Application Development
* Dockerfile Creation
* Docker Image Building
* Docker Container Execution
* Image Versioning and Tagging
* Docker Hub Integration
* Image Distribution and Deployment

---

## Learning Outcomes

After completing this project, I learned:

* Docker fundamentals
* Image vs Container concepts
* Docker networking and port mapping
* Docker image versioning
* Docker Hub image management
* Containerized application deployment
* Basic DevOps container workflow

---

