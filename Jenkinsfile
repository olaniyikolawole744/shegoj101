pipeline {
    agent any
    
    stages {
        stage('Authenticate jenkins into docker.') {
            steps {
                sh 'ls && cd shege && ls && sudo usermod -a -G docker jenkins && service restart jenkins'
                }
            }

        stage('Create Docker Image.') {
            steps {
                sh 'ls && cd shege && ls && docker build -t olanini:latest .'
                }
            }

        stage('Run docker Image.') {
            steps {
                sh 'docker run -p 9999:8080 -e loginname=myname -e loginpass=mypass -e api_key=*****  olanini'
                }
            }
        }
    }

