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
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin '
                }
            }

        stage('Push Docker Image to Dockerhub.') {
            steps {
                sh 'docker tag direction-dev:latest olaniyikolawole744/olanini && docker push olaniyikolawole744/olanini'
                }
            }

        stage('Pull Docker Image from Dockerhub.') {
            steps {
                sh 'docker pull olaniyikolawole744/olanini:latest'
                }
            }

        stage('Run Docker Image.') {
            steps {
                sh 'docker run -d -p 9999:8080 -e loginname=myname -e loginpass=mypass -e api_key=*****  olanini'
                }
            }
        }
    }

