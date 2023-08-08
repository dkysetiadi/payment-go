pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'dkysetiadi/golang'
                    label 'docker'
                }
            }
            steps {
                echo 'build image golang'
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