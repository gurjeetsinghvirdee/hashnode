---
title: "Day 2: Setting Up Appwrite Locally"
seoTitle: "Set Up Appwrite Locally - Day 2 of 30 Days of Appwrite"
seoDescription: "Learn how to set up Appwrite locally on your machine using Docker and Docker Compose. Get started with the 30 Days of Appwrite series."
datePublished: Mon Dec 16 2024 22:09:44 GMT+0000 (Coordinated Universal Time)
cuid: cm4rl8acn000109jp2knhgjrq
slug: day-2-setting-up-appwrite-locally
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1734347772438/eb7c0fd0-22db-495f-9da5-a6b073c0e921.png
tags: backend, databases, appwrite

---

Welcome back to the 30 Days of Appwrite series! Yesterday, we introduced Appwrite and discussed its key features and benefits. Today, we will focus on setting up Appwrite locally on your machine. This will allow you to have a development environment ready for the upcoming days where we explore more features and functionalities.

### Prerequisites
Before we begin, make sure you have the following installed on your machine:
- **Docker: ** Appwrite uses Docker to manage its services. If you don't have Docker installed, you can download it from the official [Docker Website](https://www.docker.com/get-started/).
- **Docker Compose: ** This is included in Docker Desktop for Windows and Mac. Linux users might need to install it separately.
- **Git: ** We will clone the Appwrite repository from GitHub, so having Git installed is necessary.

### Step-by-Step Guide
### Step 1: Install Docker and Docker Compose
#### 1. Install Docker:
- For **Windows and Mac: ** Download and install Docker Desktop from the [Docket Website](https://www.docker.com/get-started/).
- For **Linux**: Follow the official Docket installation guide for your distribution.

#### 2. Install Docker Compose (if not included with Docker Desktop):
- For **Windows and Mac: ** Docker Compose is included with Docker Desktop.
- For **Linux: ** You can install Docker Compose using the following command:
```bash
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

### Step 2: Install Git
#### 1. Install Git:
- For **Windows: ** Download and install Git from the [Git Website](https://git-scm.com/downloads/win).
- For **Mac: ** You can install Git using Homebrew with the following command: 
```bash
brew install git
``` 
- For **Linux: ** You can install Git using your package manager. For example, on Ubuntu:
```bash
sudo apt-get update
sudo apt-get install git
```

### Step 3: Clone the Appwrite Repository
1. Open your terminal or command prompt.
2. Clone the Appwrite repository from GitHub:
```bash
git clone https://github.com/appwrite/appwrite.git
```
This will create an `appwrite` directory on your local machine.

### Step 4: Navigate to the Appwrite Directory
1. Change your directory to the newly cloned `appwrite` folder:
```bash
cd appwrite
```

### Step 5: Start Appwrite Using Docker Compose
1. Appwrite provides a `docker-compose.yml` file that makes it easy to start all necessary services. Run the following command to start Appwrite:
```bash
docker-compose up -d
```
The `-d` flag runs the containers in detached mode, meaning they will run in the background.

### Steps 6: Verify the installation
Once the containers are up and running, you can verify the installation by opening your web browser and navigating to:
```bash
https://localhost/v1
```
You should see a JSON response indicating that Appwrite is running successfully.

### Step 7: Manage Appwrite with Docker Commands
After the initial setup, you can manage Appwrite using Docker commands. Here are some useful commands:
#### Start Appwrite
To start Appwrite after it has been stopped:
```bash
docker-compose start
```
#### Stop Appwrite
To stop Appwrite:
```bash
docker-compose stop
```
#### Restart Appwrite:
To restart Appwrite:
```bash
docker-compose restart
```
#### Check the Status of Appwrite Services
To check the status of Appwrite services:
```bash
docker-compose ps
```
#### Manage Individual Containers
If you prefer to manage individual containers directly, you can use the following Docker commands:
- **List All Running Containers: **
```bash
docker ps
```
- **Start a Specific Container: ** First, find the container ID or name using `docker ps -a`, then start it:
```bash
docker start <container_id_or_name>
```
- **Stop a Specific Container: **
```bash
docker stop <container_id_or_name>
```
- **Restart a Specific Container **
```bash
docker restart <container_id_or_name>
```
- **View Logs of a Specific Container: **
```bash
docker logs <container_id_or_name>
```
- **Access the Shell of a Running Container: **
```bash
docker exec -t <container_id_or_name> /bin/sh
```

### Step 8: Remove Appwrite
If you ever need to remove Appwrite completely, you can use:
```bash
docker-compose down
```
This command will stop and remove the containers, networks, and volumes defined in the `docker-compose.yml` file.

### Troubleshooting
If you encounter any issues during the setup process, here are a few common troubleshooting steps:
- **Check Docker Logs: ** You can check the logs of the Appwrite containers to diagnose any issues. Use the following command:
```bash
docker-compose logs
```
- **Restart Containers: ** Sometimes, restarting the containers can resolve issues. Use the following command to stop and restart the containers:
```bash
docker-compose down
docker-compose up -d
```
- **Check System Resources: ** Ensure that your system has enough resources *(CPU, RAM)* to run Docker and the Appwrite containers.

### Additional Resources
- [Appwrite Documentation](https://appwrite.io/docs)
- [Docker Documentation](https://docs.docker.com/)
- [Docker Compose Documentation](https://docs.docker.com/compose/)

### Conclusion
Congratulations! You have successfully set up Appwrite locally on your machine and learned how to manage it using Docker commands. This setup will serve as the foundation for our upcoming explorations of Appwrite's features and functionalities.

Stay tuned for tomorrow's post, where we will dive into the Appwrite console and understand its various components and how to use them effectively.