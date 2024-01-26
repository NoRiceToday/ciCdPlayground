pipeline {
    agent any

    tools {
        nodejs 'yarn'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/jenkinsci/jenkins.git'
            }
        }
        stage('Build') {
            steps {
                sh 'yarn'
                sh 'yarn build'
            }
        }
        stage('Test') {
            steps {
                sh 'yarn test'
                sh 'yarn test:e2e'
            }
        }
        stage('Results') {
            steps {
                junit 'reports/*.xml'
            }
        }
    }
}
