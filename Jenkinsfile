pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials ('dockerhub-id')
    }
    stages {
        stage('Build Docker Image.') {
            steps {
                sh 'ls && cd shege && ls && docker build -t olaniyikolawole744/olanini:latest .'
                }
            }
        
        stage('Login to Dockerhub.') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | DOCKER -u $DOCKERHUB_CREDENTIALS_USR --password-stdin '
                }
            }

        stage('Push Docker Image to docker.io.') {
            steps {
                sh 'docker tag olanini olaniyikolawole744/olanini && docker push olaniyikolawole744/olanini'
                }
            }

        stage('Run Docker Image.') {
            steps {
                sh 'docker run -d -p 9999:8080 -e loginname=myname -e loginpass=mypass -e api_key=*****  olanini'
                }
            }
        
        
        }
    }

