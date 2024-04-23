pipeline {
    agent any

    stages {
        stage('one') {
            steps {
                echo "i am stage one"
                sh '''echo hello world
                echo hai '''
            }
        }
        stage('two') {
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