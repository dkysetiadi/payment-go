pipeline {
    agent any
    stages {
        stage('Build'){
            image 'dkysetiadi/golang'
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