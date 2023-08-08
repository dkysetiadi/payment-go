pipeline {
    agent any
    stages {
        stage('Build'){
            agent {
                docker {
                    image 'dkysetiadi/golang'
                    label 'docker'
                }
            }
        steps {
            echo 'Build app golang'
            sh '''
            #/bin/sh
            go version
            '''
        }
            }
        }
        stage('Test'){
            steps {
                echo 'Test app'
            }
        }
        stage('Deploy'){
            steps {
                echo 'Deploy app'
            }
        }
    }