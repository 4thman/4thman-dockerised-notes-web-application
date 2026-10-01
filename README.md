Markdown
# Notes Web Application

A full-stack Node.js & Express notes management application containerized with Docker and deployed to Microsoft Azure. This project demonstrates end-to-end containerization, cloud deployment across multiple Azure services, and database management using PostgreSQL.

---

## Architecture & Deployment Strategies

This application has been successfully containerized and deployed across three distinct cloud architectures on Microsoft Azure:

1. **Azure Container Instances (ACI):** Serverless, lightweight container deployment for rapid testing and standalone instances.
2. **Web App for Containers + Azure Database for PostgreSQL:** Managed platform-as-a-service (PaaS) setup using App Service paired with a managed PostgreSQL server.
3. **Azure Virtual Machine (VM) + Docker Compose:** Infrastructure-as-a-service (IaaS) multi-container orchestration running both the web app and database containers on a single Linux VM.

---

## Repository Structure

```text
├── .gitignore
├── docker-compose.yml
├── Dockerfile
├── package.json
├── package-lock.json
├── server.js
└── README.md
Local Setup & Run
Prerequisites
Docker Desktop installed

Git

Running with Docker Compose
Clone the repository:

Bash
git clone [[https://github.com/4thman/4thman-dockerised-notes-web-application.git]]
cd notes-app
Start the application stack:

Bash
docker compose up -d
Access the application:

Open http://localhost:3000 in your browser.

Azure VM Deployment
Deploying via Docker Compose on Azure VM
SSH into your Azure Virtual Machine:

Bash
ssh azureuser@<YOUR_VM_PUBLIC_IP>
Setup and launch the containers:

Bash
mkdir notes-app && cd notes-app
# Add your docker-compose.yml configuration
docker compose up -d
Open Port 3000 in Azure Network Security Group (NSG):

Bash
az vm open-port --resource-group notes-prod-rg --name notes-vm --port 3000
Access the web app:

Navigate to http://<YOUR_VM_PUBLIC_IP>:3000 in your browser.

Environment Configuration
Variable	Description	Default Value
DB_HOST	Database Hostname	db
DB_PORT	PostgreSQL Port	5432
DB_USER	Database User	appuser
DB_PASSWORD	Database Password	Hagital123.
DB_NAME	Database Name	notesdb
PORT	Express Server Port	3000
