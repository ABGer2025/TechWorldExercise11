## TechWorldExercise11

DevOps Bootcamp AWS EKS, CI/CD, and autoscaling project.


## App Folder Overview

The `app` folder contains the Node.js web application and all supporting files:

- **server.js**: Main Express server serving `index.html` and profile images.
- **index.html**: Web page listing team members and their projects.
- **images/**: Contains profile images (`profile-andrea.jpg`, `profile-ari.jpeg`).
- **package.json**: Project metadata, dependencies (`express`, `jest`), and scripts.
- **server.test.js**: Simple Jest test to verify `index.html` exists.
- **Dockerfile**: Containerizes the app for production use.
- **docker-compose.yml**: Compose setup for local development and testing.
- **package-lock.json**: Dependency lock file for reproducible builds.

The app exposes port 3000 and serves the main page and images. It is used for Kubernetes/Fargate deployment and CI/CD automation.


## Exercises 1-6 Summary

**EXERCISE 1: Create EKS cluster**
- Create an EKS cluster with eksctl, 3 EC2 nodes, and 1 Fargate profile.

**EXERCISE 2: Deploy MySQL and phpMyAdmin**
- Deploy MySQL and phpMyAdmin on EC2 nodes using Kubernetes manifests.

**EXERCISE 3: Deploy Node.js Application**
- Deploy Node.js app on Fargate with 3 replicas using Kubernetes manifests.

**EXERCISE 4: Automate Deployment**
- Set up automatic deployment to the cluster with AWS CodeBuild (Build project: TechWorldExercise11) and GitHub Actions workflow ([GitHub Actions](https://github.com/ABGer2025/TechWorldExercise11/actions)).
- GitHub Actions workflow file: `.github/workflows/ci-cd.yml`

**EXERCISE 5: Use ECR as Docker Repository**
- Use ECR repository called `techworldexercise11` for Docker images.

**EXERCISE 6: Configure Autoscaling**
- Configure autoscaling to scale down to a minimum of 1 pod when underutilized and a maximum of 3 pods when fully utilized, using Kubernetes HPA.

## Key Files

- [app/Dockerfile](app/Dockerfile)
- [app/docker-compose.yml](app/docker-compose.yml)
- [k8s/mysql2.yaml](k8s/mysql2.yaml)
- [k8s/phpmyadmin.yaml](k8s/phpmyadmin.yaml)
- [k8s/nodejs-app.yaml](k8s/nodejs-app.yaml)
- [k8s/nodejs-app-hpa.yaml](k8s/nodejs-app-hpa.yaml)

## Notes

- CI/CD runs on the `main` branch.
- ECR is used for Docker image storage.
- Autoscaling is managed by Kubernetes HPA.
