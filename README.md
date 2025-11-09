# Hayio DevOps Circle: Beginner’s Path

A structured, beginner-friendly guide to learning DevOps fundamentals. This repository is part of the Hayio DevOps Circle community and provides a clear, stage-based path to help new learners progress from core DevOps concepts to automation and cloud practices.

How to Use This Repo:
- Follow the stages in order or pick the ones most relevant to your goals.
- Learn at your own pace; join the WhatsApp Beginners Hub for guidance and peer support.
- Stages are cumulative: later stages build on earlier concepts and exercises.
- Use the task lists to apply what you learn with small, practical exercises.

---

## Learning Overview
| Stage | Focus | Key Skills |
|--------|--------|------------|
| 1 | Introduction to DevOps | Mindset, Culture, SDLC |
| 2 | Version Control | Git, GitHub |
| 3 | Automation (CI/CD) | Pipelines, Workflows |
| 4 | Containers | Docker Basics |
| 5 | Infrastructure as Code | Terraform, Cloud Setup |
| 6 | Observability and Security | Monitoring, IAM, Best Practices |

---

## Stage 1: Introduction to DevOps
Now that you are getting started, Stage 1 introduces the purpose and principles that drive DevOps.

- [Microsoft Learn: What is DevOps?](https://learn.microsoft.com/en-us/devops/what-is-devops)
- [AWS DevOps Overview](https://aws.amazon.com/devops/what-is-devops/)
- [Atlassian: CI/CD Explained](https://www.atlassian.com/continuous-delivery/ci-vs-ci-vs-cd)

**Outcome:** You’ll know what DevOps is and why it exists.

Tasks:
- Read 2-3 introductory articles and write a 1-paragraph summary of DevOps goals.
- Map a simple SDLC for a sample app (identify stages and handoffs).
- Identify one manual bottleneck in the SDLC and propose an automation to address it.
- Join the community links and introduce yourself.

---

## Stage 2: Git and GitHub
After understanding the culture, Stage 2 covers the collaboration tools you will use daily.

See detailed guide: [Stage 2 — Git & GitHub](./docs/stage2.md)

Install:
- [Git](https://git-scm.com/downloads)
- [VS Code](https://code.visualstudio.com/)
- [GitHub Account](https://github.com/)

Learn:
- How to create a repository  
- Making your first commit  
- Branching and pull requests  
- Collaborating with others  

**Outcome:** You can manage code and version history like a DevOps engineer.

Tasks:
- Install Git and configure user.name and user.email.
- Create a new repo, add a README, commit and push the first commit.
- Create a feature branch, implement a small change, open a PR and merge via review.
- Simulate a merge conflict and resolve it locally.
- Add a basic CONTRIBUTING.md with branching and PR rules.

---

## Stage 3: CI/CD Foundations
Once code is versioned, Stage 3 shows how to automate builds, tests, and deployments.

Core Ideas:
- What Continuous Integration (CI) means  
- What Continuous Delivery (CD) means  
- Sample workflow using GitHub Actions  

Example Workflow (GitHub Actions):
```yaml
name: Simple CI
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - run: echo "Building project..."
```

**Outcome:** You can automate simple workflows triggered by code changes.

Tasks:
- Create a GitHub Actions workflow that runs on PRs and executes basic tests or an echo command.
- Add unit tests (or a simple smoke test) and make the CI fail when tests fail.
- Add a build-and-push job to push artifacts (or Docker image) to a registry in a protected branch.
- Add a status badge to the README showing the main workflow status.
- Implement a simple release workflow (tag -> create release artifact).

References & Tools:
- GitHub Actions (docs): https://docs.github.com/actions
- Jenkins (CI server): https://www.jenkins.io/
- GitLab CI/CD: https://docs.gitlab.com/ee/ci/
- CircleCI: https://circleci.com/docs/
- Azure Pipelines: https://learn.microsoft.com/azure/devops/pipelines/
- Best practices: pipeline as code, small fast jobs, test automation, artifact versioning

---

## Stage 4: Containers
See detailed guide: [Stage 4 — Containers](./stage-4-containers.md)

## Stage 5: Infrastructure as Code
See detailed guide: [Stage 5 — IaC (Terraform)](./stage-5-iac.md)  
Includes cloud provider examples (AWS, GCP, Azure) in the detailed guide.

## Stage 6: Observability and Security
See detailed guide: [Stage 6 — Observability & Security](./stage-6-observability.md)

---

## Community
Join the Hayio DevOps Circle discussions:
- WhatsApp Beginners Hub: [Join Here](https://chat.whatsapp.com/IARjC1yFBfQ2duKw2y13Hd)
- Website: [https://hayio.net](https://hayio.net)

---

## Coming Next / Roadmap
- Stage 4: Containers, Docker and container registries
- Stage 5: Infrastructure as Code, Terraform and cloud setup
- Stage 6: Observability and Security, monitoring, tracing and IAM

---

## Motto
Learn, Build, Secure, The African Way.
