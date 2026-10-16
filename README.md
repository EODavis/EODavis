<h1 align="center">Hi, I’m E.O.Davis 👋</h1>
<p align="center">
  <strong>Software Engineer • Backend & Infrastructure • Automation-first • MLOps</strong>
</p>

<p align="center">
  <a href="https://github.com/EODavis">
    <img alt="GitHub" src="https://img.shields.io/badge/GitHub-EODavis-181717?style=for-the-badge&logo=github" />
  </a>
  <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img alt="Node.js" src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" />
  <img alt="Linux" src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" />
  <img alt="Docker" src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
  <img alt="CI/CD" src="https://img.shields.io/badge/CI--CD-GitHub%20Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white" />
</p>

---

## About me
I design and build reliable backend systems and developer-facing tooling with an automation-first mindset. I love shipping well-tested services, reproducible deployments, and CI/CD pipelines that make engineering teams faster and safer.
* Background in data science and machine learning.
* Building hands-on skills in DevOps, Linux, cloud infrastructure, and CI/CD.
* Exploring MLOps, AI engineering, and software architecture.
* Focused on practical projects, automation, testing, and technical documentation.
* Committed to continuous learning through building and improving real-world projects.


Core focus areas:
- Backend APIs and microservices (Python + Node.js)
- Containerized deployments on Linux using Docker
- CI/CD automation with GitHub Actions
- Observability, testing, and repeatable developer workflows
- Programming & Data: Python, SQL, data processing
- Systems & Infrastructure: Linux, Bash, networking
- DevOps & Automation: Git, GitHub, CI/CD, Docker, Nginx
- Machine Learning: scikit-learn, model evaluation, MLflow
- Emerging Areas: MLOps, AI engineering, agentic AI, cloud architecture

---

## Tech stack (focused)
- Languages: Python (FastAPI / Flask, Django), JavaScript / TypeScript (Node.js, Express)
- Runtime & OS: Linux (Ubuntu, Debian)
- Containerization: Docker, Docker Compose
- CI/CD: GitHub Actions (build, test, lint, security scanning)
- Datastores & messaging: PostgreSQL, Redis (recommended patterns)
- Testing & quality: pytest, Jest, ESLint, pre-commit hooks
- Dev tools: Git, Make, shell scripting, Dockerfile best practices

---

## Principles I follow
- Automation-first: every repetitive step becomes a script or CI job
- Reproducible environments: Docker images + pinned dependencies
- Small, fast tests in CI, with clear failure signals
- Secure-by-default: minimal image surface, dependency scanning
- Observability: logs, metrics, and readiness/liveness checks

---

## Featured projects
(Replace placeholders with your actual repos and short highlights.)

- MLOps NLP Ticket Classifier — An evolving project exploring machine learning and MLOps workflows.

- HNG Stage 2 DevOps — Practical DevOps implementation and deployment exercises.

- Server Stats — A project focused on server monitoring and Linux administration.

- API Platform — https://github.com/EODavis/api-platform  
  FastAPI + PostgreSQL, Dockerized, CI: tests, lint, and DB migration checks.

- Worker Queue — https://github.com/EODavis/worker-queue  
  Node.js (Bull / Redis) background processing, containerized, integrated with GitHub Actions for deployment.

- DevOps Toolkit — https://github.com/EODavis/devops-toolkit  
  Reusable Docker images, utility scripts, and GitHub Actions workflow templates for standardizing CI pipelines.

---

## CI / GitHub Actions (recommended)
Common CI jobs I include:
- build: lint + typecheck + unit tests
- security: dependency scanning (Dependabot / Snyk)
- container: build and smoke-test Docker image
- release: tag → build + push image + create release

Example status badge (replace with your repo/workflow):
[![CI](https://github.com/EODavis/project-name/actions/workflows/ci.yml/badge.svg)](https://github.com/EODavis/project-name/actions/workflows/ci.yml)

Example minimal workflow (save as .github/workflows/ci.yml)
```yaml
name: CI
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    services:
      postgres:
        image: postgres:14
        env:
          POSTGRES_PASSWORD: postgres
        ports: ['5432:5432']
        options: >-
          --health-cmd pg_isready
          --health-interval 10s
          --health-timeout 5s
          --health-retries 5
    steps:
      - uses: actions/checkout@v4
      - name: Set up Python
        uses: actions/setup-python@v4
        with: python-version: '3.11'
      - name: Install deps
        run: pip install -r requirements.txt
      - name: Run tests
        run: pytest -q
```

---

## Docker & local development
- Use multi-stage builds for small production images.
- Keep a `docker-compose.yml` for local stacks (db + cache + app).
- Example local workflow:
  1. git clone git@github.com:EODavis/project-name.git
  2. cp .env.example .env && edit variables
  3. docker compose up --build
  4. docker compose exec app make migrate && docker compose exec app make test

Dockerfile pattern (high-level)
```Dockerfile
FROM python:3.11-slim AS base
WORKDIR /app
COPY pyproject.toml poetry.lock ./
RUN pip install --upgrade pip && pip install poetry && poetry install --no-dev

FROM base AS runtime
COPY . .
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
```

---

## Local setup (quick)
1. Clone the repo
2. Create .env from .env.example with secrets
3. Start local stack: docker compose up --build
4. Run tests: docker compose exec app pytest
5. Lint and typecheck: docker compose exec app flake8 && mypy .

---

## How I work / contribution
- Clear, focused PRs with a short description and test coverage
- Small incremental changes with a passing CI pipeline
- Use semantic commit messages and keep CHANGELOGs for releases
- I respond best to issues labeled with "good first issue" or "help wanted"

---

## Contact
- GitHub: https://github.com/EODavis
- Email: immanueldavis1@gmail.com
- LinkedIn: https://www.linkedin.com/in/emmanuel-davis-a8b114104/

---

<p align="center">
  <em>“Ship smaller, automate more, and measure everything.”</em>
</p>
