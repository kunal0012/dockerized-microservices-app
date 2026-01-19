
# Dockerized Microservices Application

## 📌 Problem Statement
Running a multi-service application using virtual machines introduces unnecessary overhead, slow provisioning, and higher resource usage. This project demonstrates how the same multi-tier application can be containerized using Docker to achieve faster deployments and better resource efficiency.

---

## 🏗️ Architecture Overview
The application stack consists of the following Docker containers:

- **Nginx** – Reverse proxy and entry point
- **Apache Tomcat** – Application server
- **MySQL** – Database service
- **Memcached** – Caching layer
- **RabbitMQ** – Message broker

All containers communicate over a dedicated Docker bridge network.

---

## 🧰 Tools & Technologies
- Docker
- Docker Compose
- Linux
- Nginx
- Apache Tomcat
- MySQL
- Memcached
- RabbitMQ

---

## ⚙️ Containerization Approach
- Each service runs in its own Docker container.
- Docker Compose is used to define and manage all services.
- Service discovery is handled internally by Docker networking.
- Nginx acts as a reverse proxy to forward traffic to the application container.
- Environment variables are used for service configuration.

---

## 🚀 How to Run the Project
1. Install Docker and Docker Compose
2. Clone this repository:
   ```bash
   git clone <repo-url>
   cd dockerized-microservices-app
3. Make a directory in the VM (root user) "mkdir /compose/" then use vim editor and create a file docker-compose.yml
4. Copy the docker code from repository to your own docker YAML file
5. Run command docker compose up or docker compose up -d(to run command in background) 
5. Use nginx container IP in your local browser to run the application. 

## What I Learned

1. Differences between VM-based and container-based architectures
2. Docker networking and service discovery
3. Managing multi-container applications using Docker Compose
4. Simplifying deployments using containers