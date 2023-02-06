pipeline {
    agent any
    environment {
        ENV_URL = 'pipleline.global.com'
    }
    stages {
        stage ('one') {
            steps {
                echo " I am Stage one step"
                echo "ENV URL is ${ENV_URL}"
            }
        }
        stage ('two') {
            environment {
                ENV_URL = 'stage.global.com'
            }
            steps {
                echo " I am Stage two step"
            }
        }
        stage ('three') {
            steps{
                echo " I am Stage three step"
            }
        }
        stage ('four') {
            steps {
                sh '''echo hello world
                echo hey
                echo good moring'''
            }
        }
    }
}