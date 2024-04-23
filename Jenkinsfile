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
            }
        }
        stage('two') {
            environment {
                ENV_URL = "wwww.amazn.com"
            }
            steps {
                echo "i am stage two"
          
            }
        }
        stage('three') {
            steps {
                echo "i am stage two"
            }
        }
    }
}