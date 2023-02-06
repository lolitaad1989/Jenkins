pipeline {
    agent {
        label'ANSIBLE'
    }
    environment {
        ENV_URL = 'pipleline.global.com'
        SSH_CRED = credentials('SSH_CRED')
    }
    options {
        buildDiscarder(logRotator(numToKeepStr: '3'))
        disableConcurrentBuilds()
        disableResume() 
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    tools {
        maven 'mvn-387' 
    }
    stages {
        stage ('Parallel-stage') {
            parallel {
                stage ('one') {
                    steps {
                        echo " I am Stage one step"
                        echo "ENV URL is ${ENV_URL}"
                        sh 'mvn --version'
                        sh 'hostname'
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
    }
}