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
}