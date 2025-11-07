# Stage 4 — Containers (Docker Basics)

Overview:
- Why containers matter: portability, isolation, reproducible runtime.
- Image vs container, layering, and immutability.

Install:
- Docker Engine (Linux): https://docs.docker.com/engine/install/
- Docker CLI basics: docker build, run, images, ps, logs

Learn:
- Build an image: `docker build -t myapp:latest .`
- Run a container: `docker run --rm -p 8080:80 myapp:latest`
- Inspect: `docker images`, `docker ps`, `docker logs <container>`
- Multi-stage builds, slimmer base images, and image scanning (Trivy)

Cloud (run containers in cloud):
- AWS: Amazon ECS / ECR, AWS Fargate
- GCP: Google Cloud Run / GKE, Container Registry / Artifact Registry
- Azure: Azure Container Instances / AKS, Azure Container Registry

Tasks:
- Containerize a simple web app (create Dockerfile + .dockerignore).
- Build and run locally; fix failure logs.
- Push image to a registry (Docker Hub or GHCR or cloud registry).
- Deploy the image to a cloud runtime (Cloud Run, ACI, or a small ECS task).
- Add an image-scan step to your CI pipeline.

Exercises:
- Create Dockerfile for a sample app and commit it.
- Automate build-and-push in GitHub Actions (use secrets for registry).
- Deploy to free tier Cloud Run or ACI and verify endpoint.

Outcome:
- Containerize apps, push images to a registry, and run them locally or in cloud.

References:
- Docker docs: https://docs.docker.com/
- Trivy (image scanning): https://github.com/aquasecurity/trivy
- Cloud run guides: AWS/ECS, GCP/Cloud Run, Azure/ACI