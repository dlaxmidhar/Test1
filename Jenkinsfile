pipeline {
    agent {
        docker {
            image 'node:16'
        }
    }
    stages {
        stage('install playwright') {
            steps {
                sh '''
                npm i -D @playwright/test
                npx playwright install
                '''
            }
        }
        stage('help') {
            steps {
                sh 'npx playwright test --help'
            }
        }
        stage('test') {
            steps {
                sh '''
                npx playwright test --list
                npx playwright test
                '''
            }
        }
    }
}

