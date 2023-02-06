pipeline {
    agent any
    environment {
        ENV_URL = 'pipleline.global.com'
        SSH_CRED = credentials('SSH_CRED')
    }
    options {
        buildDiscarder(logRotator(numToKeepStr: '3'))
        disableConcurrentBuilds()
        disableResume() 
        timeout(time: 1, unit: 'MINUTES')
    }
    stages {
        stage ('one') {
            steps {
                echo " I am Stage one step"
                echo "ENV URL is ${ENV_URL}"
                sleep 300
            }
        }
        stage ('two') {
            environment {
                ENV_URL = 'stage.global.com'
            }
            steps {
                echo " I am Stage two step"
                echo "ENV URL is ${ENV_URL}"
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
                echo good moring
                env
                '''
            }
        }
    }
}