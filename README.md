# Secure CI/CD Pipeline Project

## Overview

This project demonstrates a **secure CI/CD pipeline** using **Docker** and **GitHub Actions**. The pipeline automates:

* Building a containerized application
* Running security scans using **Trivy**
* Pushing the Docker image to **GitHub Container Registry (GHCR)**
* Optional deployment to a server using **Docker Compose**

It follows **DevSecOps principles**, integrating security checks directly into the CI/CD workflow.

## Project Structure

```
secure_cicd/
├── app/                     # Sample Python/Flask application
│   └── main.py
├── Dockerfile               # Docker image definition for the app
├── docker-compose.yml       # Docker Compose configuration for deployment
├── .github/
│   └── workflows/
│       └── ci.yml           # GitHub Actions CI/CD pipeline
└── README.md                # Project documentation
```

## CI/CD Workflow

The pipeline triggers on **push** or **pull request** to the `main` branch:

1. **Build Docker image** from the `app/` folder
2. **Scan Docker image** for vulnerabilities using Trivy
3. **Push Docker image** to GHCR
4. **Optional deployment** with Docker Compose

## Running Locally

1. Clone the repository:

```
git clone https://github.com/YOUR_USERNAME/secure_cicd.git
cd secure_cicd
```

2. Build the Docker image:

```
docker build -t secure_cicd:local ./app
```

3. Run the container:

```
docker run -d -p 5000:5000 secure_cicd:local
```

4. Open in browser:

```
http://localhost:5000
```

## Security Integration

* **Trivy** automatically scans the Docker image in the CI pipeline
* Ensures images are **vulnerability-free before deployment**

## Key Skills Demonstrated

* Docker & containerization
* GitHub Actions CI/CD workflow
* DevSecOps practices (security scanning)
* Project structuring for automation
* Troubleshooting and pipeline debugging

## Notes

* Deployment step can be enabled on a server/VM with Docker Compose
* GitHub Actions workflow can be extended to other environments or cloud providers

## License

MIT License
