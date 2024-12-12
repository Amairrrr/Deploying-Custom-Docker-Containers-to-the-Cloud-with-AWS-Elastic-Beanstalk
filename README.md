# Deploying-Custom-Docker-Containers-to-the-Cloud-with-AWS-Elastic-Beanstalk

# Containers on Elastic Beanstalk
![image](https://github.com/user-attachments/assets/2d3c42e0-12c1-4214-ac76-68cf50abf349)

## Overview

This project demonstrates my expertise in containerization using Docker and deploying containerized applications to the cloud with AWS Elastic Beanstalk. I created a custom container image, ran it locally, and successfully deployed it to a scalable and efficient cloud platform. This project showcases my hands-on experience with modern DevOps tools and cloud services, emphasizing fast and efficient software delivery.

---

## Why Containers Matter

Containers have revolutionized software development by simplifying how applications are packaged, shared, and deployed. They ensure consistency across environments, speed up deployment times, and make applications portable across platforms. In this project, I leveraged Docker to containerize a web application and AWS Elastic Beanstalk to deploy it to the cloud seamlessly.

---

## Key Technologies Used

- **Docker**: For containerization and building a custom image.
- **AWS Elastic Beanstalk**: For deploying and managing the application in the cloud.
- **Nginx**: A high-performance web server to serve the web application.

---

## Steps to Recreate the Project

### 1. Install Docker

1. Download and install [Docker Desktop](https://www.docker.com/products/docker-desktop) for your operating system.
2. Verify installation:
   ```bash
   docker --version
   ```

---

### 2. Run a Pre-Built Container

1. Pull and run the official Nginx container image:
   ```bash
   docker run -d -p 80:80 nginx
   ```
2. Open your browser and navigate to `http://localhost` to see the default Nginx page.

---

### 3. Build a Custom Container Image

1. **Set Up Project Directory**:
   ```bash
   mkdir ~/Desktop/Johnlewis
   cd ~/Desktop/Johnlewis
   ```

2. **Create and Write a Dockerfile**:
   ```bash
   touch Dockerfile
   ```
   Add the following content to the `Dockerfile`:
   ```dockerfile
   FROM nginx:latest
   COPY index.html /usr/share/nginx/html/
   EXPOSE 80
   ```

3. **Create a Simple Web Page**:
   ```bash
   touch index.html
   ```
   Add the following content to `index.html`:
   ```html
   <!doctype html>
   <html>
     <head>
       <title>My Web App</title>
     </head>
     <body>
       <h1>Hello from my custom Docker image!</h1>
     </body>
   </html>
   ```

4. **Build the Image**:
   ```bash
   docker build -t my-web-app .
   ```

---

### 4. Run the Custom Container

1. Stop any container already using port 80:
   ```bash
   docker ps
   docker stop <container_id>
   ```
2. Run your custom container:
   ```bash
   docker run -d -p 80:80 my-web-app
   ```
3. Visit `http://localhost` to see your custom web page.

---

### 5. Deploy to AWS Elastic Beanstalk

#### Elastic Beanstalk Configuration:

1. **Prepare Deployment Files**:
   - Ensure `Dockerfile` and `index.html` are in the root directory.
   - Create a ZIP file containing these files:
     ```bash
     zip deployment.zip Dockerfile index.html
     ```

2. **Set Up Elastic Beanstalk**:
   - Navigate to AWS Elastic Beanstalk in the AWS Management Console.
   - Create a new application:
     - Application Name: `MyWebApp`
     - Platform: Docker
     - Upload Code: Use the ZIP file created earlier.

3. **Environment Configuration**:
   - Environment Tier: Web Server.
   - Instance Settings: Enable Public IP address.
   - Root Volume: General Purpose SSD (10 GB).
   - System Monitoring: Basic (Free Tier Eligible).
   - Deployment Policy: All at once.

4. **Deploy Application**:
   - Click **Create Application**.
   - Once the deployment is complete, click the domain link provided by Elastic Beanstalk to see your live application.

---

### 6. Update the Application

1. Modify `index.html`:
   ```html
   <h1>
     If I can see this, it means Elastic Beanstalk has deployed an updated version of my work.
   </h1>
   ```
2. Recreate the ZIP file:
   ```bash
   zip deployment.zip Dockerfile index.html
   ```
3. Deploy the updated ZIP file to Elastic Beanstalk.

---

## Outcome

By completing this project, I:
- Mastered Docker for containerization.
- Deployed a scalable application using AWS Elastic Beanstalk.
- Gained practical experience in managing cloud-based applications.

---

## Key Skills Demonstrated

- **Containerization**: Building and managing Docker containers.
- **Cloud Deployment**: Deploying and scaling applications using AWS services.
- **Web Development**: Creating and serving custom web content.
- **Problem Solving**: Troubleshooting deployment issues and optimizing configurations.

---
---
