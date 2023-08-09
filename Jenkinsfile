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
                sh '''
                #/bin/sh
                go version
                GOCACHE=/tmp/ GOOS=linux GOARCH=amd64 go build -o goapp main.go
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