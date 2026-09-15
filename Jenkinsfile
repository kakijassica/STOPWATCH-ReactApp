```groovy
pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Check Node') {
            steps {
                bat 'node --version'
                bat 'npm --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm ci'
            }
        }

        stage('React Build') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t stopwatch:latest .'
            }
        }

        stage('Stop Old Container') {
            steps {
                bat 'docker stop stopwatch-container 2>NUL || exit /b 0'
                bat 'docker rm stopwatch-container 2>NUL || exit /b 0'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d --name stopwatch-container -p 3000:80 stopwatch:latest'
            }
        }

        stage('Verify Deployment') {
            steps {
                bat 'docker ps'
            }
        }

        stage('Validate CloudFormation') {
            steps {
                bat 'aws cloudformation validate-template --template-body file://cloudformation.yaml'
            }
        }

        stage('Deploy CloudFormation') {
            steps {
                bat 'aws cloudformation deploy --template-file cloudformation.yaml --stack-name stopwatch-cloudformation --   parameter-overrides EnvironmentName=dev'
            }
        }
    }
}
```
