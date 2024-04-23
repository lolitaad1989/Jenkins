pipeline {
    agent any

    environment {
        ENV_URL = "wwww.flipkart.com"
        SSH_CRED = credentials('SSH_CRED')
    }

    options {
        buildDiscarder(logRotator(numToKeepStr: '1')) 
        disableResume()
        timeout(time: 1, unit: 'MINUTES')
    }

        tools {
        maven 'apache-maven-3.9.1' 
    }

    // triggers { pollSCM('*/3 * * * *') }

    parameters {
        string(name: 'PERSON', defaultValue: 'Ms Lolita', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages {
        stage('one') {
            steps {
                echo "i am stage one"
                sh '''echo hello world
                echo hai 
                env '''
                echo "ENV URL is ${ENV_URL}"
                sh "hostname"
                sh "mvn --version"
                // sh "sleep 300"
            }
        }
        stage('two') {
            environment {
                ENV_URL = "wwww.amazn.com"
            }
            steps {
                echo "i am stage two"
                echo "ENV URL is ${ENV_URL}"
            }
        }
        stage('three') {
            steps {
                echo "i am stage three"
            }
        }
    }
}