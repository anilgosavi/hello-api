pipeline {
    agent any
    environment {
        DOCKER_IMAGE = 'hello-api:latest'
    }
    stages {
        stage("Clone Repository") {
            steps {
                echo "Cloning repository"
                checkout scm
            }
        }
        stage("Build Docker Image") {
            steps {
                echo "Building Docker Image"
                sh  "docker build -t ${DOCKER_IMAGE}."
            }
        }
        post{
            success {
                echo "Image built successfully"
            }
            failure {
                echo "Image build failed"   
            }
        }            
    }
}

