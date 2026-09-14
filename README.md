# ⚡ DevOps Health API

<p align="center">
  <strong>Production-style Python service demonstrating containerization, automated testing, CI quality gates and container security.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python 3.12"/>
  <img src="https://img.shields.io/badge/Flask-3.1-000000?style=for-the-badge&logo=flask&logoColor=white" alt="Flask"/>
  <img src="https://img.shields.io/badge/Docker-Containerized-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"/>
  <img src="https://img.shields.io/badge/GitHub_Actions-CI-2088FF?style=for-the-badge&logo=githubactions&logoColor=white" alt="GitHub Actions"/>
  <img src="https://img.shields.io/badge/Trivy-Security-1904DA?style=for-the-badge&logo=aqua&logoColor=white" alt="Trivy"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="MIT License"/>
</p>

<p align="center">
  <a href="https://github.com/yeshpal-devops/devops-health-api/actions/workflows/ci.yml"><img src="https://github.com/yeshpal-devops/devops-health-api/actions/workflows/ci.yml/badge.svg" alt="CI"/></a>
  <img src="https://img.shields.io/github/last-commit/yeshpal-devops/devops-health-api?style=flat-square" alt="Last commit"/>
  <img src="https://img.shields.io/github/repo-size/yeshpal-devops/devops-health-api?style=flat-square" alt="Repo size"/>
</p>

## 🎯 Project Overview

`devops-health-api` is intentionally small so the engineering focus stays on **DevOps practices rather than application complexity**.

It demonstrates a practical delivery path:

**Code → Test → Build → Scan → Run**

### What this project demonstrates

- REST API health endpoints
- Automated testing with Pytest
- Reproducible Docker image builds
- Non-root container execution
- Docker Compose for local operations
- GitHub Actions CI
- Trivy vulnerability scanning
- Least-privilege CI permissions
- Container health checks

## 🏗️ Architecture

```mermaid
graph LR
    A[Developer] --> B[Git Push / Pull Request]
    B --> C[GitHub Actions]
    C --> D[Pytest]
    D --> E[Docker Build]
    E --> F[Trivy Scan]
    F --> G[Validated Image]
    G --> H[Docker Compose / Runtime]
    H --> I[/health]
```

## 🔄 CI Pipeline

```text
Checkout
   ↓
Python 3.12
   ↓
Install dependencies
   ↓
Run Pytest
   ↓
Build Docker image
   ↓
Scan HIGH / CRITICAL vulnerabilities
   ↓
CI result
```

The workflow is path-aware, so CI executes when project files change. The repository uses read-only `contents` permissions by default.

## 📁 Repository Structure

```text
.
├── .github/
│   └── workflows/
│       └── ci.yml
├── app.py
├── test_app.py
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
├── .dockerignore
├── .gitignore
├── LICENSE
└── README.md
```

## 🚀 Run Locally

### Option 1 — Python

```bash
python -m venv .venv

# Windows
.venv\Scripts\activate

# Linux/macOS
source .venv/bin/activate

pip install -r requirements.txt
python app.py
```

Open:

- `http://localhost:8080/`
- `http://localhost:8080/health`

### Option 2 — Docker Compose

```bash
docker compose up --build
```

Stop:

```bash
docker compose down
```

## 🧪 Testing

```bash
pytest -q
```

The test suite validates both the service metadata endpoint and the health endpoint.

## 📡 API Reference

| Method | Endpoint | Purpose |
|---|---|---|
| `GET` | `/` | Service metadata |
| `GET` | `/health` | Health status + UTC timestamp |

Example health response:

```json
{
  "status": "healthy",
  "timestamp": "2026-09-14T12:00:00+00:00"
}
```

## 🔐 Security Controls

| Control | Implementation |
|---|---|
| Non-root runtime | Container runs as UID `10001` |
| Dependency pinning | Explicit package versions |
| Image scanning | Trivy HIGH/CRITICAL gate |
| CI permissions | Least privilege by default |
| Secret hygiene | No application secrets stored in source |
| Runtime health | Docker healthcheck against `/health` |

## 🧰 Technology Stack

| Area | Technology |
|---|---|
| Application | Python 3.12, Flask |
| Testing | Pytest |
| Containers | Docker, Docker Compose |
| CI/CD | GitHub Actions |
| Security | Trivy |
| Runtime | Linux container |

## 💼 Portfolio Value

This project is designed to show practical understanding of:

- CI/CD pipeline design
- Docker image lifecycle
- Linux container fundamentals
- Automated quality gates
- Container security
- Git workflows
- Operational health checks
- Production-minded repository structure

## 🛣️ Roadmap

Planned extensions for a larger cloud DevSecOps implementation:

- Terraform-managed Azure infrastructure
- Azure Container Registry
- Azure Container Apps deployment
- GitHub OIDC → Azure authentication
- Azure Key Vault integration
- Checkov IaC security scanning
- SonarQube quality gates
- SBOM generation
- Dev → QA → Prod promotion
- Deployment approvals and rollback
- Azure Monitor / Application Insights
- Prometheus metrics

## 👤 Author

**Yesh Pal** — DevOps / Cloud Engineer  
GitHub: [@yeshpal-devops](https://github.com/yeshpal-devops)

---

<p align="center">
  <strong>Build → Test → Scan → Ship</strong>
</p>
