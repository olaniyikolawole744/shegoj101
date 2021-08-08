pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID     = credentials ('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials ('AWS_SECRET_ACCESS_KEY')
        AWS_DEFAULT_REGION    = 'us-east-1'
    }

    stages {
        stage('Build AMI') {
            steps {
                sh 'cd 2021-devopstraining-miniproject && mvn clean package && cp target/*.jar /tmp/direction.jar'
            }
        }
        