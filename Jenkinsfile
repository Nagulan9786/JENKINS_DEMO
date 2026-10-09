pipeline {
    agent any
    environment {
        IMAGE = "demo-app:${BUILD_NUMBER}"
    }
    stages {
        stage('Test') {
            steps { sh 'python3 -m unittest -v' }
        }
        stage('Build Image') {
            steps { sh 'docker build -t $IMAGE .' }
        }
        stage('Run Image') {
            steps { sh 'docker run --rm $IMAGE' }
        }
    }
    post {
        always { sh 'docker image prune -f' }
    }
}
