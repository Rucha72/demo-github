pipeline {
    agent any

    parameters {
        choice(
            name: 'ENVIRONMENT',
            choices: ['DEV', 'PROD'],
            description: 'Select deployment environment'
        )
        booleanParam(
            name: 'RUN_TESTS',
            defaultValue: true,
            description: 'Run tests before deployment?'
        )
    }
    stages {
        stage('Build') {
            steps {
                bat 'echo Building application...'
            }
        }
        stage('Test') {
            when {
                expression {
                    params.RUN_TESTS == true
                }
            }
            steps {
                bat 'echo Running tests...'
            }
        }
        stage('Deploy to DEV') {
            when {
                expression {
                    params.ENVIRONMENT == 'DEV'
                }
            }
            steps {
                bat 'echo Deploying application to DEV...'
            }
        }
        stage('Deploy to PROD') {
            when {
                expression {
                    params.ENVIRONMENT == 'PROD'
                }
            }
            steps {
                bat 'echo Deploying application to PROD...'
            }
        }
    }
}
