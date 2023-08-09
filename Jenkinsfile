pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'golang:alpine3.16'
                    label 'docker'
                }
            }
            steps {
                echo 'build image golang'
                sh '''
                #/bin/sh
                go version
                '''
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