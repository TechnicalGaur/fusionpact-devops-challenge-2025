## Fusionpact DevOps Gauntlet Challenge

A complete two-tier application with fault-tolerant architecture, comprehensive monitoring, and automated CI/CD pipeline deployed on AWS.


🌟 Overview
The Fusionpact DevOps Gauntlet Challenge demonstrates mastery of modern DevOps practices through a complete two-tier application deployment. This project showcases containerization, cloud deployment, monitoring, and automated CI/CD workflows.

Challenge Requirements
Level	Requirement	Implementation	Status
Level 1	Cloud Deployment (30%)	Docker + AWS EC2 + Docker Compose	✅ Complete
Level 2	Monitoring & Observability (30%)	Prometheus + Grafana + Metrics	✅ Complete
Level 3	CI/CD Automation (30%)	GitHub Actions Pipeline	✅ Complete
Docs	SOP + Screenshots (10%)	PDF Guide + Screenshots	✅ Complete
🏆 Key Achievements
Fault-Tolerance: Health checks, restart policies, graceful shutdowns

Observability: Metrics, logging, dashboards for infrastructure and application

Automation: Full CI/CD pipeline, automated deployment on every commit

Scalability: Container-based, ready for further orchestration

Security: Non-root containers, security groups, secrets management



✨ Features
🚀 Application Features
Responsive Frontend: Modern HTML/CSS interface, real-time status

RESTful API: FastAPI backend with Prometheus /metrics

Health Monitoring: Built-in /health endpoints for frontend/backend

Real-time Data: Dynamic API with test and demo endpoints

Multi-platform: Containerized for local/dev/prod use

📊 Monitoring
Prometheus Metrics: Automatic FastAPI instrumentation, custom metrics

Grafana Dashboards: Pre-built infra and app dashboards, live metrics

Alerting & Logging: Easily extendable for custom alerts

🔄 DevOps
Automated Testing: Pytest unit/regression tests run on every push

Docker Compose: Multi-container orchestration, plug-and-play

CI/CD Pipeline: GitHub Actions triggers build, test, deploy on push

Zero-downtime Deployment: Rolling container updates, health checks

Infra as Code: Declarative setup - easy reproducibility and modification

🚀 Quick Start
Prerequisites
Docker 20.10+ and Docker Compose 2.0+

Git

AWS account and EC2 access (for cloud deployment)

GitHub account for CI/CD

Local Development
bash
# Clone repository
git clone https://github.com/yourusername/fusionpact-devops-challenge.git
cd fusionpact-devops-challenge

# Start all services
docker-compose up -d

# View component status
docker-compose ps
Access Points
Service	URL	Credentials
Frontend	http://localhost	-
Backend API	http://localhost:8000	-
API Docs	http://localhost:8000/docs	-
Prometheus	http://localhost:9090	-
Grafana	http://localhost:3000	admin/admin123
Validation Commands
bash
curl -f http://localhost                 # Frontend
curl -f http://localhost:8000/health     # Backend health
curl -f http://localhost:8000/api/data   # API endpoint
curl -f http://localhost:9090/api/v1/targets  # Prometheus targets
🛠️ Detailed Setup
1. Local Setup
bash
git clone https://github.com/yourusername/fusionpact-devops-challenge.git
cd fusionpact-devops-challenge

# Ensure Docker and Compose are installed
docker --version
docker-compose --version

docker-compose up --build -d
docker-compose logs -f
2. AWS Cloud Deployment
Launch EC2 instance (t3.medium recommended)

Configure Security Group for ports: 22, 80, 3000, 8000, 9090

SSH and install Docker/Compose:

bash
ssh -i your-key.pem ec2-user@your-instance-ip

sudo yum update -y
sudo yum install -y docker git
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -a -G docker ec2-user

sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

git clone https://github.com/yourusername/fusionpact-devops-challenge.git
cd fusionpact-devops-challenge
docker-compose up -d
🔁 Challenge Levels & Completion
✅ Level 1: Cloud Deployment (30%)
Containerize frontend (Nginx) & backend (FastAPI)

Orchestrate with docker-compose.yml

Deploy to AWS EC2, public accessibility

Persistence via Docker volumes

✅ Level 2: Monitoring & Observability (30%)
Prometheus configuration to scrape /metrics

Grafana dashboards for infra/app metrics

Real-time data visualization

✅ Level 3: CI/CD Automation (30%)
GitHub Actions pipeline: test, build, push, deploy

Automated Docker image registry push

SSH-based deployment to AWS



📊 Monitoring
Prometheus /metrics
Sample queries:

text
rate(http_requests_total[5m])
histogram_quantile(0.95, rate(http_request_duration_seconds_bucket[5m]))
process_cpu_seconds_total
process_resident_memory_bytes / 1024 / 1024
Grafana Dashboards
Infrastructure: CPU, memory, containers

Application: request rate, latency, error counts

Pre-configured for instant monitoring

🔄 CI/CD Pipeline
Workflow steps:

On push: code checkout → testing → build/push Docker images → deploy to EC2

Configuration: .github/workflows/deploy.yml

Secrets: DockerHub, AWS credentials

🔧 Troubleshooting
Container issues: docker-compose logs service-name

Prometheus scraping: docker exec fusionpact-prometheus wget -qO- http://backend:8000/metrics

Pipeline errors: Check GitHub Actions logs, verify secrets, SSH/registry access

🤝 Contributing
Fork this repo

Create feature branch (git checkout -b feature/my-feature)

Commit and push

Open Pull Request for review

📜 License
MIT License - see LICENSE








