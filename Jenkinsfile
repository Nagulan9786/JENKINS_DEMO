pipeline {
    agent any

    environment {
        APP_NAME = 'demo-app'
    }

    options {
        timeout(time: 5, unit: 'MINUTES')
    }

    stages {
        stage('Build') {
            steps { echo "Building ${APP_NAME}" }
        }
        stage('Test') {
            steps { sh 'echo running tests && exit 0' }
        }
        stage('Deploy') {
            when { branch 'main' }
            steps { echo 'Deploying...' }
        }
    }

    post {
        success { echo 'Pipeline passed' }
        failure { echo 'Pipeline failed' }
        always  { echo 'Cleanup runs either way' }
    }
}
