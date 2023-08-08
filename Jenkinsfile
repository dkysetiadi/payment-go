pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'dkysetiadi/golang'
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