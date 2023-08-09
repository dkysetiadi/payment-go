pipeline {
    agent {
        label 'docker'
    }
    environment {
        GCP_SERVICE_ACCOUNT = credentials{'service-account-jenkins'}
    }
    stages {
        stage('Build') {
            steps {
                echo 'build image golang'
                sh 'docker build -t gcr.io/ferrous-module-395010/golang-apps:1 .'
            }
        }
        stage('Push') {
            steps {
                echo 'push to gcr'
                sh 'cat '
                sh 'docker push gcr.io/ferrous-module-395010/golang-apps:1'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy image'
            }
        }
    }
}