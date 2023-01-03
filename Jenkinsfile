pipeline {
    agent none

    stages{   
        stage('Clone backend Repository for PROD environment') {
            agent { label 'debian' }
            steps {
                git branch: 'main', url: 'https://github.com/gisela91/dockerfile.git'
                echo 'Cloned Backend Project'
            }
        }
        stage('Build backend for PROD with docker-compose') {
            agent { label 'debian' }
            steps {
                sh 'docker-compose up -d'
                echo 'Build PROD backend'
            }
        }
        stage('Clone frontend Repository for PROD environment') {
            agent { label 'debian' }
            steps {
                git branch: 'main', url: 'https://github.com/gisela91/dockerfile.git'
                echo 'Cloned Frontend Project'
            }
        }
        stage('Build frontend for PROD with docker-compose') {
            agent {label 'debian'}
            steps {
                sh 'docker-compose up -d frontend'
                echo 'Build PROD frontend'
            }
        }
    }
}
