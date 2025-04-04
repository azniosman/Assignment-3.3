# Assignment 3.3

A simple Flask application containerized with Docker and configured for CI/CD with GitHub Actions.

## Project Overview

This repository contains a simple Flask API that demonstrates:

- Basic Flask application structure
- Docker containerization
- Automated CI/CD with GitHub Actions
- Automated Docker image deployment to DockerHub

## Application Structure

- `app.py`: The main Flask application
- `requirements.txt`: Python dependencies
- `Dockerfile`: Instructions for building the Docker image
- `.github/workflows/docker-build-push.yml`: GitHub Actions workflow configuration

## API Endpoints

| Endpoint  | Method | Description               |
| --------- | ------ | ------------------------- |
| `/`       | GET    | Returns a welcome message |
| `/health` | GET    | Health check endpoint     |

## Local Development

### Prerequisites

- Python 3.11+
- Docker

### Running Locally with Python

```bash
# Clone the repository
git clone https://github.com/azniosman/Assignment-3.3.git
cd Assignment-3.3

# Create a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run the application
python app.py
```

### Running Locally with Docker

```bash
# Build the Docker image
docker build -t flask-sample .

# Run the container
docker run -p 5000:5000 flask-sample
```

## Testing the API

```bash
# Test the root endpoint
curl http://localhost:5000/

# Test the health check endpoint
curl http://localhost:5000/health
```

## CI/CD Pipeline

This project uses GitHub Actions to automatically build and push the Docker image to DockerHub when changes are pushed to the main branch.

### Workflow Features

- Automatically triggered on pushes to the main branch
- Uses Docker Buildx for efficient builds
- Securely authenticates with DockerHub using GitHub Secrets
- Implements caching to speed up builds

### GitHub Secrets Configuration

Before the workflow will work properly, you need to add the following secrets to your GitHub repository:

1. `DOCKERHUB_USERNAME`: Your DockerHub username
2. `DOCKERHUB_TOKEN`: A DockerHub access token (not your password)

To add these secrets:

1. Go to your GitHub repository
2. Click on "Settings" → "Secrets and variables" → "Actions"
3. Click "New repository secret" and add each secret

## Docker Image

The Docker image is available on DockerHub at:

```

```
