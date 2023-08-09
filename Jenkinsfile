pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'build image golang'
                sh 'docker build -t gcr.io/ferrous-module-395010/golang-apps:1 .'
            }
        }
        stage('Test') {
            steps {
                echo 'tes image golang'
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