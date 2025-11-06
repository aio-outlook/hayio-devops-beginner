# Stage 4 — Containers (Docker Basics)

Overview:
- Why containers matter
- Image vs container, portability, and immutability

Install:
- Docker Desktop or docker-engine (Linux): https://docs.docker.com/get-docker/

Learn:
- Build an image: `docker build -t myapp:latest .`
- Run a container: `docker run --rm -p 8080:80 myapp:latest`
- Inspect images and containers: `docker images`, `docker ps`, `docker logs <id>`

Exercises:
- Containerize a simple web app
- Push an image to Docker Hub or GitHub Container Registry

Outcome: You can containerize apps and run them locally or in CI.

References:
- Docker docs: https://docs.docker.com/
- Best practices: small images, multi-stage builds, security scanning