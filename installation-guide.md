# Jenkins Installation and Docker Plugin Configuration Guide

This guide provides step-by-step instructions for installing Jenkins and configuring it to work seamlessly with Docker plugins. Jenkins is a powerful continuous integration and continuous delivery (CI/CD) tool, and Docker integration enhances its capabilities by enabling efficient containerized workflows.

## Prerequisites

Before you begin, ensure you have the following prerequisites in place:

- A Linux-based server or virtual machine (e.g., Ubuntu, CentOS, or Debian).
- An internet connection for downloading packages.
- Administrative or root access to the server.

## Step 1: Install Jenkins

### Ubuntu

1. Update the package repository:

   ```shell
   sudo apt update
2. Install Java Development Kit (JDK):

```shell
Copy code
sudo apt install openjdk-11-jdk
```

3. Add the Jenkins repository key:

```shell
Copy code
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -

4. Add the Jenkins repository:

```shell
Copy code
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
```
5. Install Jenkins:

```shell
Copy code
sudo apt update
sudo apt install jenkins
```
6. Start Jenkins and enable it to start on boot:

```shell
Copy code
sudo systemctl start jenkins
sudo systemctl enable jenkins
```

7. Retrieve the initial Jenkins administrator password:

```shell
Copy code
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
8. Access Jenkins in your web browser using your server's IP address or domain and port 8080 (e.g., http://your_server_ip:8080). Enter the initial administrator password when prompted.

# for CentOS

(Install Java and Jenkins similarly to the Ubuntu steps, adapting the package manager commands as needed.)

# Step 2: Install Docker

1. Update the package repository:

```shell
Copy code
sudo apt update
```
2. Install Docker:

```shell
Copy code
sudo apt-install docker.io
```

3. Grant Jenkins user and Ubuntu user permission to the Docker daemon:

```shell
Copy code
sudo su -
usermod -aG docker jenkins
usermod -aG docker ubuntu
systemctl restart docker
```

4. Restart Jenkins:

```shell
Copy code
http://<ec2-instance-public-ip>:8080/restart
```
Step 3: Install Docker Pipeline Plugin in Jenkins
Log in to Jenkins.

Go to "Manage Jenkins" > "Manage Plugins."

In the "Available" tab, search for the "Docker Pipeline" plugin.

Select the plugin and click the "Install" button.

After installation, restart Jenkins to activate the plugin:

```shell
Copy code
http://<ec2-instance-public-ip>:8080/restart
```

Step 4: Configure Jenkins and Docker Integration
Your Jenkins installation is now configured to work seamlessly with Docker. You can create pipelines and jobs that leverage Docker containers for building, testing, and deploying your applications.

Additional Resources

Jenkins Documentation

Docker Documentation
