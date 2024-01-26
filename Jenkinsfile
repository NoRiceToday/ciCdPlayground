pipeline {
    agent any

    tools {
        nodejs 'yarn'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/NoRiceToday/ciCdPlayground'
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
        stage('Deploy') {
            steps {
            }
        }
    }
}
