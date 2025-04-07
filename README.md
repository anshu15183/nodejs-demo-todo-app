# Node.js Demo App with CI/CD (GitHub Actions + Docker)

This project demonstrates a complete CI/CD pipeline using **GitHub Actions** and **Docker** for a simple Node.js application.  
On every push to the `main` branch, the app is automatically built and deployed as a Docker image to **DockerHub**.

---

## Tech Stack

- Node.js  
- Docker  
- GitHub Actions  
- DockerHub  

---

## CI/CD Workflow Overview

The GitHub Actions pipeline performs the following steps:

1. Checkout the repository  
2. Set up Node.js environment  
3. Install dependencies using `npm install`  
4. Run tests (`npm test`)  
5. Build Docker image from `Dockerfile`  
6. Login to DockerHub using GitHub Secrets  
7. Push the Docker image to DockerHub  

### Trigger

- The workflow triggers on every **push to the `main` branch**

---

## GitHub Secrets Used

| Secret Name        | Description             |
|--------------------|-------------------------|
| `DOCKER_USERNAME`  | DockerHub Username      |
| `DOCKER_PASSWORD`  | DockerHub Password or Access Token |

> Set these secrets in:  
**GitHub → Repo → Settings → Secrets and variables → Actions**

---

## Docker Instructions

### Build the Docker Image Locally

```bash
docker build -t your-username/nodejs-demo-app:latest .
```

### Run the Image Locally

```bash
docker run -p 3000:3000 your-username/nodejs-demo-app
```
