# DevOps Lab App

A minimal Python Flask web application that is containerized with Docker and automatically built and tested using a GitHub Actions CI pipeline.

This project was created as a DevOps class activity at Riphah International University.

## Project Overview

This project demonstrates three core DevOps practices:

- **Containerization:** The application is packaged in a lightweight Docker image based on `python:3.10-slim`.
- **Version Control:** The source code is managed with Git and hosted on GitHub.
- **Continuous Integration (CI):** A GitHub Actions workflow builds the Docker image and tests the container on every push to the `main` branch.

## Technologies Used

- Python 3.10
- Flask 3.0.0
- Docker
- Git and GitHub
- GitHub Actions

## Project Structure

```
devops-lab-app/
├── .github/
│   └── workflows/
│       └── ci-pipeline.yml
├── app.py
├── requirements.txt
├── Dockerfile
└── README.md
```

| File | Purpose |
|------|---------|
| `app.py` | Flask application that shows a welcome message |
| `requirements.txt` | List of Python packages needed by the app |
| `Dockerfile` | Instructions to build the Docker image |
| `ci-pipeline.yml` | GitHub Actions workflow for automated build and test |

## Prerequisites

Please install the following before running the project:

- Git
- Docker Desktop

## How to Run Locally

**1. Clone the repository**

```
git clone https://github.com/YOUR-USERNAME/devops-lab-app.git
cd devops-lab-app
```

**2. Build the Docker image**

```
docker build -t devops-flask-app:v1.0 .
```

**3. Run the container**

```
docker run -d -p 5000:5000 --name flask-container devops-flask-app:v1.0
```

**4. Open the application**

Open a web browser and go to:

```
http://localhost:5000
```

The page will show: **DevOps Class Activity: Docker & GitHub Actions Pipeline Active!**

**5. Stop and remove the container (optional)**

```
docker stop flask-container
docker rm flask-container
```

## CI Pipeline

The workflow file is located at `.github/workflows/ci-pipeline.yml`.

**Trigger events:**
- A push to the `main` branch
- A pull request to the `main` branch

**Pipeline steps:**
1. **Checkout Source Code:** Copies the repository code to the GitHub runner.
2. **Build Docker Image:** Builds the Docker image from the Dockerfile.
3. **Test Container Execution:** Runs the container and checks that it is running.

The result of each run can be seen in the **Actions** tab of this repository.

## Author

**Abdul Rafay**
BS Software Engineering, Riphah International University, Islamabad