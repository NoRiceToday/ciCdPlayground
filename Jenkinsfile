pipeline {
    agent any

    tools {
        nodejs 'yarn'
    }

    stages {
        stage('Build') {
            steps {
                step{
                    git checkout 'https://github.com/NoRiceToday/ciCdPlayground'
                    yarn
                    yarn build
                }
            }
        }
        stage('Test') {
            steps {
                yarn test
                yarn test:e2e
            }
        }
        stage('Deploy') {
            steps {
                junit 'reports/*.xml'
            }
        }
    }
}