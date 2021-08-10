pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID     = credentials ('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials ('AWS_SECRET_ACCESS_KEY')
        AWS_DEFAULT_REGION    = 'us-east-1'
    }

    stages {
        stage('Create Docker Image.') {
            steps {
                sh 'ls && cd shege && ls && docker build -t sudo docker build -t olanini:latest .'
                }
            }

        stage('Run docker Image.') {
            steps {
                sh 'sudo docker run -p 9999:9999 -e loginname=myname -e loginpass=mypass -e api_key=*****  olanini'
                }
            }
        }
    }

