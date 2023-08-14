pipeline {
    agent {
        label 'docker'
    }
    environment {
        GCP_SERVICE_ACCOUNT = credentials('service_account_jenkins')
        KUBE_CONFIG = credentials('config_kube')
    }
    stages {
        stage('Build') {
            steps {
                echo 'build image golang'
                sh 'docker build -t gcr.io/ferrous-module-395010/golang-apps:${BUILD_NUMBER} .'
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
                sh 'whoami'
                sh 'helm upgrade --install goapp dicky-charts/application'
            }
        }
    }
}
