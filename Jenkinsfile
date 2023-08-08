pipeline {
    agent any
    stages {
        stage('Build'){
            agent {
                docker {
                    image 'dkysetiadi:golang'
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
        stage('Test'){
            echo 'test image'
        }
        stage('Deploy'){
            eccho 'deploy image'
        }
    }
}