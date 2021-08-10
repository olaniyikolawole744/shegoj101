pipeline {
    agent any
    
    stages {
        stage('Create Docker Image.') {
            steps {
                sh 'ls && cd shege && ls && docker build -t olaniyikolawole744/olanini:latest .'
                }
            }

        stage('Push Docker Image to docker,io.') {
            steps {
                sh 'docker tag olanini olaniyikolawole744/olanini:latest && docker push olaniyikolawole744/olanini:latest'
                }
            }

        stage('Run Docker Image.') {
            steps {
                sh 'docker run -d -p 9999:8080 -e loginname=myname -e loginpass=mypass -e api_key=*****  olanini'
                }
            }
        
        
        }
    }

