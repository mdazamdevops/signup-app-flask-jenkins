 # DevOps Internship Task 2 – Creating a Simple Jenkins Pipeline for CI/CD

## Elevate Labs: Empowering the Future of DevOps
This project is a testament to the high-quality, hands-on learning experience provided by Elevate Labs. Their internship program is dedicated to empowering the next generation of DevOps professionals by offering practical, real-world challenges that build foundational skills and a deep understanding of modern software development practices.
---
### Overview
The objective of this task is to set up a basic Jenkins pipeline to automate the process of building and deploying an application. This task introduces Jenkins as a powerful automation server and demonstrates how to define a pipeline using a Jenkinsfile to create a reliable and repeatable CI/CD workflow.

### Objective

* Set up a Jenkins instance (or use a cloud instance).

* Create a Jenkinsfile to define the pipeline stages.

* Configure Jenkins to trigger the pipeline on each code commit.

* Implement stages for build, test, and deploy.

### Tools & Technologies
* Jenkins – The core automation server for CI/CD.

* Docker – Used for containerizing the application.

* Git – For version control and triggering the pipeline.

## Project Structure
```

├── .github/
│   └── workflows/
│       └── main.yml
├── backend/
│   ├── app.py
│   ├── requirements.txt
│   └── Dockerfile
└── frontend/
    ├── index.html
    ├── server.js
    ├── package.json
    └── Dockerfile
├── docker-compose.yml
├── Jenkinsfile
└── README.md
```

## Step-by-Step Implementation

## 1. Install Jenkins
Install Jenkins on a local machine or set up a cloud instance. Ensure Docker is also installed on the same machine or on a remote agent connected to Jenkins.

## 2. Create the Jenkinsfile
A Jenkinsfile is a text file that defines the Jenkins pipeline using either a Declarative or Scripted syntax. For this task, we will use a Declarative pipeline. The file must be named Jenkinsfile and placed in the root of the project repository.

## Here is a sample Jenkinsfile with common stages:
```
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                // You can add your build commands here, e.g.,
                // sh 'docker build -t my-app .'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // You can add your test commands here, e.g.,
                // sh 'docker run my-app npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // You can add your deployment commands here, e.g.,
                // sh 'docker push my-app'
                // sh 'ssh user@server "docker pull my-app && docker stop container && docker run -d -p 80:80 my-app"'
            }
        }
    }
}
```

## 3. Configure Jenkins Job
Create a new "Pipeline" job in Jenkins.

Configure the job to connect to your GitHub repository.

In the "Pipeline" section, select "Pipeline script from SCM" and specify your Git repository URL.

Set the script path to Jenkinsfile.

Enable the "Poll SCM" option or configure a webhook to trigger the pipeline automatically on code commits.

## 4. Trigger the Pipeline
Commit and push changes to your repository. This will automatically trigger the Jenkins job. You can monitor the progress on the Jenkins dashboard and view the logs for each stage.

# Learning Outcomes

### By completing this task, you will:

* Understand how to automate the deployment process with Jenkins.
* Learn to create a Jenkinsfile for defining a pipeline.
* Gain experience configuring Jenkins jobs for CI/CD.
* Enhance your DevOps project portfolio.

## Interview Questions to Practice
1. What is Jenkins, and how is it used in CI/CD?

2. What is a Jenkinsfile?

3. How do you create and configure Jenkins pipelines?

4. What are some common stages in a Jenkins pipeline?

5. What is the difference between a declarative and scripted Jenkins pipeline?

## Company Credit

This task is created under the DevOps Internship Program by Elevate Labs. The company’s vision is to empower students and professionals with real-world DevOps expertise through hands-on training and mentorship.

# Creator
Name: Mohd Azam Uddin

Role: DevOps Intern

Contribution: Implemented a simple Jenkins pipeline for CI/CD, providing a foundational understanding of Jenkins automation. 

---
