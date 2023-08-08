pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'gcr.io/ferrous-module-395010/dkysetiadi'
                }
            }
            steps {
                echo 'build image'
            }
        }
        stage('Test') {
            steps {
                echo 'test image'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy image'
            }
        }
    }
}