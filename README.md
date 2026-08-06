# 🚀 Task 3: CI/CD Pipeline with Docker using GitHub Actions

![GitHub Actions](https://img.shields.io/badge/GitHub-Actions-blue?logo=githubactions)
![Docker](https://img.shields.io/badge/Docker-Container-blue?logo=docker)
![Nginx](https://img.shields.io/badge/Nginx-Web%20Server-green?logo=nginx)
![CI/CD](https://img.shields.io/badge/CI%2FCD-Automated-success)
![License](https://img.shields.io/badge/License-MIT-yellow)

---

## 📖 Project Overview

This project demonstrates a **real-world DevOps CI/CD pipeline** using **GitHub Actions**, **Docker**, and **Docker Hub**.

Whenever code is pushed to the **main** branch, GitHub Actions automatically:

* ✅ Checks out the source code
* ✅ Builds a Docker image
* ✅ Tags the image with the GitHub Actions build number
* ✅ Pushes the image to Docker Hub
* ✅ Runs the Docker container
* ✅ (Bonus) Deploys the latest image to an AWS EC2 instance

This project follows modern DevOps practices and is ideal for learning CI/CD automation.

---

# 🎯 Objective

Automate Docker image creation and deployment using GitHub Actions.

---

# 🏗️ Architecture

```text
                Developer

                    │
          Git Push to GitHub

                    │
                    ▼

            GitHub Actions Trigger

                    │
     ┌──────────────┴──────────────┐
     │                             │
     ▼                             ▼

 Checkout Source              Build Docker Image

                    │

                    ▼

          Login to Docker Hub

                    │

                    ▼

           Push Docker Image

                    │

                    ▼

         Run Docker Container

                    │

                    ▼

          Application Running

                    │

            (Optional Bonus)

                    ▼

             Deploy to AWS EC2
```

-----

# 📂 Project Structure

```text----
Task-3-CICD-Docker/
│
├── .github/
│   └── workflows/
│       └── docker-ci.yml
│
├── app/
│   ├── index.html
│   └── nginx.conf
│
├── Dockerfile
├── docker-compose.yml
├── .dockerignore
├── README.md
└── LICENSE
```
<img width="1672" height="941" alt="2" src="https://github.com/user-attachments/assets/b56ac105-6ceb-433b-ac37-810b160ed342" />



---

# 🛠️ Technologies Used

* GitHub Actions
* Docker
* Docker Hub
* Nginx
* Git
* YAML
* Bash
* AWS EC2 (Optional)

---

# ⚙️ Prerequisites

Before running this project, ensure you have:

* Git
* Docker Desktop or Docker Engine
* Docker Hub Account
* GitHub Account
* Visual Studio Code (Recommended)
* AWS EC2 Instance (Optional)

---

# 📦 Clone the Repository

```bash
git clone https://github.com/yourusername/Task-3-CICD-Docker.git

cd Task-3-CICD-Docker
```

---

# 🐳 Build Docker Image

```bash
docker build -t cicd-demo .
```

---

# ▶️ Run Docker Container

```bash
docker run -d \
-p 8080:80 \
--name cicd-demo \
cicd-demo
```

Visit:

```
http://localhost:8080
```

---

# 🔄 CI/CD Workflow

The GitHub Actions pipeline performs the following stages:

## Stage 1

✔ Checkout Repository

---

## Stage 2

✔ Login to Docker Hub

---

## Stage 3

✔ Build Docker Image

---

## Stage 4

✔ Tag Image

Example:

```
cicd-demo:15
```

and

```
cicd-demo:latest
```

---

## Stage 5

✔ Push Image to Docker Hub

---

## Stage 6

✔ Run Docker Container

---

## Stage 7 (Bonus)

✔ Deploy to AWS EC2

---

# 🔐 GitHub Secrets

Add the following repository secrets:

| Secret Name     | Description                      |
| --------------- | -------------------------------- |
| DOCKER_USERNAME | Docker Hub Username              |
| DOCKER_PASSWORD | Docker Hub Personal Access Token |
| EC2_HOST        | AWS Public IP                    |
| EC2_USER        | SSH Username                     |
| EC2_SSH_KEY     | Private SSH Key                  |

---

# ▶ GitHub Actions Workflow

The workflow automatically triggers whenever code is pushed to:

```text
main
```

Workflow stages:

```
Checkout

↓

Docker Login

↓

Docker Build

↓

Docker Push

↓

Run Container

↓

Deploy (Optional)
```

---

# 🐳 Docker Commands Used

Build image

```bash
docker build -t image-name .
```

Run container

```bash
docker run -d -p 8080:80 image-name
```

Login

```bash
docker login
```

Push image

```bash
docker push username/image
```

Pull image

```bash
docker pull username/image
```

Stop container

```bash
docker stop container-name
```

Remove container

```bash
docker rm container-name
```

---

# 🚀 Deploy to AWS EC2

The deployment stage performs:

* Pull latest Docker image
* Stop existing container
* Remove old container
* Start new container
* Keep application running using Docker restart policy

---

# 📊 Expected Output

After every Git push:

```
✔ Workflow Triggered

✔ Source Checked Out

✔ Docker Image Built

✔ Image Tagged

✔ Docker Hub Login Successful

✔ Image Pushed

✔ Container Started

✔ Website Accessible

✔ Deployment Successful (AWS Bonus)
```

---

# 📸 Sample Pipeline

```
Git Push

      │

      ▼

GitHub Actions

      │

      ▼

Build Docker Image

      │

      ▼

Push to Docker Hub

      │

      ▼

Run Container

      │

      ▼

Application Running
```

---

# 📚 Learning Outcomes

After completing this project, you will understand:

* GitHub Actions
* CI/CD concepts
* Docker image creation
* Docker Hub authentication
* Docker image tagging
* Container deployment
* Automated pipelines
* Cloud deployment basics
* Infrastructure automation

---

# 💡 Future Enhancements

* Kubernetes Deployment
* Helm Charts
* Trivy Security Scanning
* SonarQube Code Analysis
* Slack Notifications
* Email Notifications
* Blue-Green Deployment
* Rolling Updates
* Multi-stage Docker Builds
* GitOps using Argo CD

---

# 🐞 Troubleshooting

## Docker login failed

Verify Docker Hub credentials and Personal Access Token.

---

## Image push failed

Ensure the repository exists on Docker Hub and you have permission to push.

---

## GitHub Actions failed

Check:

* Repository Secrets
* Workflow syntax
* Dockerfile
* Branch name

---

## Container not running

Run:

```bash
docker ps -a
```

Check logs:

```bash
docker logs cicd-demo
```

---

# 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push your branch
5. Open a Pull Request

---

# 📄 License

This project is licensed under the MIT License.

---

# 👨‍💻 Author

**Sudheesh K**

**Senior Infrastructure Lead | DevOps | Cloud | Docker | Kubernetes | AWS | Terraform | Jenkins**

If you found this project helpful, consider giving it a ⭐ on GitHub!
