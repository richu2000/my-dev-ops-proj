# DevOps CI/CD Pipeline with GitHub Actions

## Project Overview

This project demonstrates a complete CI/CD pipeline using GitHub Actions, Docker, Docker Hub, and a Flask application.

The pipeline automatically:

1. Triggers on every push to the main branch.
2. Sets up Python.
3. Installs Flask dependencies.
4. Verifies the application environment.
5. Builds a Docker image.
6. Authenticates to Docker Hub using GitHub Secrets.
7. Pushes the Docker image to Docker Hub.

---

## Technologies Used

* Python 3.12
* Flask
* Docker
* Docker Hub
* GitHub Actions
* Git

---

## Project Structure

```text
my-dev-ops-proj/
│
├── .github/
│   └── workflows/
│       └── docker-ci.yml
│
├── docker-flask-app/
│   ├── app.py
│   ├── Dockerfile
│   └── README.md
│
└── terraform-devops-platform/
```

---

## GitHub Actions Workflow

### Trigger

The workflow runs automatically on every push to the main branch.

```yaml
on:
  push:
    branches:
      - main
```

---

### Pipeline Stages

#### 1. Checkout Repository

Downloads repository code to the GitHub runner.

#### 2. Setup Python

Installs Python 3.12 on the runner.

#### 3. Install Dependencies

Installs Flask using pip.

#### 4. Verify Application

Validates Flask installation.

#### 5. Docker Login

Authenticates to Docker Hub using GitHub Secrets.

#### 6. Build Docker Image

Builds the Docker image from the Dockerfile.

#### 7. Push Docker Image

Pushes the image to Docker Hub.

---

## GitHub Secrets

The following repository secrets are used:

| Secret             | Purpose                 |
| ------------------ | ----------------------- |
| DOCKERHUB_USERNAME | Docker Hub Username     |
| DOCKERHUB_TOKEN    | Docker Hub Access Token |

Secrets are securely stored in GitHub and are never exposed in workflow logs.

---

## Workflow Architecture

```text
Developer
    ↓
git push
    ↓
GitHub Repository
    ↓
GitHub Actions
    ↓
Setup Python
    ↓
Install Flask
    ↓
Build Docker Image
    ↓
Docker Login
    ↓
Push Image
    ↓
Docker Hub
```

---

## Skills Demonstrated

* Continuous Integration (CI)
* GitHub Actions
* Docker Image Build Automation
* Docker Hub Integration
* Secret Management
* CI/CD Pipeline Troubleshooting
* Automated Container Delivery

---

## Learning Outcomes

Through this project I learned:

* GitHub Actions workflow creation
* Workflow triggers and runners
* CI pipeline debugging
* Docker image automation
* Secure secret management
* Automated image publishing
* End-to-end CI/CD fundamentals

---

## Future Improvements

* Add automated testing
* Add image versioning
* Add Kubernetes deployment
* Add AWS deployment
* Add monitoring and alerts

