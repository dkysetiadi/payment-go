pipeline {
    agent {
        label 'docker'
    }
    environment {
        GCP_SERVICE_ACCOUNT = credentials('service_account_jenkins')
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
                sh 'cat "$GCP_SERVICE_ACCOUNT" | docker login -u _json_key --password-stdin https://gcr.io'  
                sh 'docker push gcr.io/ferrous-module-395010/golang-apps:${BUILD_NUMBER}'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy image'
            }
        }
    }
}