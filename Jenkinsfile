pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials ('dockerhub-id')
    }
    stages {
        stage('Login to Dockerhub') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin '
                }
            }


        stage('Build Docker Master Branch Image') {
            when{
                
                branch "main"
            }
            steps {
                sh 'ls && cd shege && ls && docker build -t olaniyikolawole744/direction-prod:latest . \
                && docker tag direction-prod:latest olaniyikolawole744/direction-prod:latest && echo "yeeeeeeexit" && docker push olaniyikolawole744/direction-prod:latest \
                && docker pull olaniyikolawole744/direction-prod && docker run -d -p 9999:8080 -e loginname=myname -e loginpass=mypass -e api_key=*****  olaniyikolawole744/direction-prod:latest'
                }
            }


        stage('Build Docker Develop Branch Image') {
            when{
                
                branch "develop"
            }
            steps {
                sh 'ls && cd shege && ls && docker build -t olaniyikolawole744/direction-dev:latest . \
                && docker tag direction-dev olaniyikolawole744/direction-dev && docker push olaniyikolawole744/direction-dev \
                && docker pull olaniyikolawole744/direction-dev:latest && docker run -d -p 9999:8080 -e loginname=myname -e loginpass=mypass -e api_key=*****  direction-dev'
                }
            }

        }
    }

