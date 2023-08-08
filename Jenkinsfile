pipeline {
    agent any
    stages {
        stage('Build'){
            agent {
                docker {
                    image 'golang:alpine'
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
}