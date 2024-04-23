pipeline {
    agent any

    environment {
        ENV_URL = "wwww.google.com"
    }

    stages {
        stage('one') {
            steps {
                echo "i am stage one"
                sh '''echo hello world
                echo hai '''
                echo "ENV URL is ${ENV_URL}"
            }
        }
        stage('two') {
            environment {
                ENV_URL = "wwww.amazn.com"
            }
            steps {
                echo "i am stage two"
                echo "ENV URL is ${ENV_URL}"
                env
            }
        }
        stage('three') {
            steps {
                echo "i am stage two"
            }
        }
    }
}