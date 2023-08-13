pipeline {
    agent {
        label 'docker'
    }
    environment {
        GCP_SERVICE_ACCOUNT = credentials('service_account_jenkins')
        KUBE_CONFIG = credentials('kubernetes_jenkins')
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
        stage('Active GCP Account') {
            steps {
                echo "Active GCP Account"
                sh 'ssh -o StrictHostKeyChecking=no -i "$ID_RSA" $GCP_SERVICE_ACCOUNT'
                sh 'ssh -o StrictHostKeyChecking=no -i "$ID_RSA" dickysetiadi64@34.101.98.183 "gcloud auth activate"'
                sh 'ssh -o StrictHostKeyChecking=no -i "$ID_RSA" dickysetiadi64@34.101.98.183 "gcloud auth list"'
                sh 'ssh -o StrictHostKeyChecking=no -i "$ID_RSA" dickysetiadi64@34.101.98.183 "gcloud container clusters get-credentials cluster-jenkins --zone asia-southeast2-a --project ferrous-module-395010"'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy image'
                sh 'helm repo add dicky-charts https://adhithia21.github.io/helm-charts/charts'
                sh 'helm upgrade --kubeconfig "$KUBE_CONFIG" --install goapp dicky-charts/application'
            }
        }
    }
}