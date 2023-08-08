pipeline {
    agent any
    stages {
        stage('Build'){
            agent {
                docker {
                    image 'dkysetiadi/golang'
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