**README for Dockerized Nginx Project on AWS Elastic Beanstalk**

**Overview**
This project demonstrates how to containerize a web application using Docker and deploy it to AWS Elastic Beanstalk. The app is served via Nginx, and the deployment process leverages AWS-managed infrastructure for scalability and simplicity.

## Project Overview

This repository includes:
- `Dockerfile`: Instructions to build a Docker image.
- `index.html`: Custom web page served by Nginx.

## Key Technologies
- **Docker**: Containerization platform.
- **Nginx**: Web server.
- **AWS Elastic Beanstalk**: Cloud deployment service.

## Steps to Deploy

1. **Build and Test Locally**:
   - Create a custom Docker image:
     ```bash
     docker build -t my-custom-image .
     ```
   - Run the container:
     ```bash
     docker run -d -p 80:80 my-custom-image
     ```
**Testing using a pre-existing container image called nginx**

     docker run -d -p 80:80 nginx

  ![Screenshot 2025-01-02 171547](https://github.com/user-attachments/assets/71101467-347b-4afa-9df9-f25604d42074)

   - Stop conflicting containers if needed.

1. **Prepare for Deployment**:
   - Ensure the `Dockerfile` and application files (e.g., `index.html`) are in the project directory.

2. **Deploy to AWS Elastic Beanstalk**:
   - Create a ZIP archive of the project files.
   - Deploy the archive via the Elastic Beanstalk console.
   - AWS will automatically manage resources, including creating an S3 bucket for storage.
![Screenshot 2025-01-02 190937](https://github.com/user-attachments/assets/335b02e2-c138-4124-85a1-a2b7af2c26d8)

3. **Clean Up**:
   - Delete unused files from the S3 bucket to save storage costs.

## Troubleshooting

- If a port conflict occurs while running the container, stop the existing container via Docker Desktop or CLI:
  ```bash
  docker stop <container-id>
