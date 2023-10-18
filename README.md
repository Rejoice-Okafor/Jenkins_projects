# Jenkins_projects
# Getting Started with Jenkins on Ubuntu

This README provides step-by-step instructions for installing Jenkins on an Ubuntu system and getting started with continuous integration and continuous delivery (CI/CD) pipelines.

## Prerequisites

- An Ubuntu server or desktop machine
- Administrative access or sudo privileges

## Installation

1. **Update Package List:**

   Ensure your package list is up to date:

   ```bash
   sudo apt update
Install Java:

Jenkins requires Java. You can install OpenJDK, an open-source implementation of the Java Platform:

bash
Copy code
sudo apt install openjdk-8-jdk
Add Jenkins Repository and Key:

Import the Jenkins repository key and add the repository to your sources list:

bash
Copy code
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
Install Jenkins:

Update your package list and install Jenkins:

bash
Copy code
sudo apt update
sudo apt install jenkins
Start Jenkins:

Start the Jenkins service and enable it to start on boot:

bash
Copy code
sudo systemctl start jenkins
sudo systemctl enable jenkins
Retrieve Initial Admin Password:

The initial Jenkins admin password can be found in the Jenkins home directory. Use the following command to retrieve it:

bash
Copy code
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
Access Jenkins Web Interface:

Open your web browser and go to http://your_server_ip:8080 or http://localhost:8080 if you are working on the server itself. Use the admin password from step 6 to unlock Jenkins.

Install Recommended Plugins:

In the Jenkins web interface, you will be prompted to install recommended plugins. Click "Install suggested plugins" to proceed.
