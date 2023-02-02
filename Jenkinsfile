pipeline {
    agent any
    stages {
        stage ('one') {
            steps {
                echo " I am Stage one step"
            }
        }
        stage ('two') {
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