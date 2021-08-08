pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID     = credentials ('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials ('AWS_SECRET_ACCESS_KEY')
        AWS_DEFAULT_REGION    = 'us-east-1'
    }

    stages {
        stage('Build App') {
            steps {
                sh 'ls && cd shege && ls && /usr/bin/mvn clean package && cp target/*.jar /tmp/direction.jar'
            }
        }

        stage('Run App') {
            steps {
                sh 'cd shege && cp target/*.jar /tmp/direction.jar && java -jar /tmp/direction.jar && loginname=segun loginpass=segun api_key=***** java -jar /tmp/direction.jar'
            }
        }
    }
}
        