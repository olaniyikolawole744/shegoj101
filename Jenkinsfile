pipeline {
    agent any
    
    stages {
        stage('Create Docker Image.') {
            steps {
                sh 'ls && cd shege && ls && docker build -t olanini:latest .'
                }
            }

        stage('Run Docker Image.') {
            steps {
                sh 'docker run -p 9999:8080 -e loginname=myname -e loginpass=mypass -e api_key=*****  olanini'
                }
            }
        }
    }

