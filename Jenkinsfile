pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out repository'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t calculator-app .'
            }
        }

        stage('Run Database Container') {
            steps {
                sh 'docker compose up -d'
            }
        }

    }
}