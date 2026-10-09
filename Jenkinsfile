pipeline {
    agent any

    parameters {
        choice(
            name: 'ENVIRONMENT',
            choices: ['DEV', 'PROD'],
            description: 'Select deployment environment'
        )
    }
    stages {
        stage('Build') {
            steps {
                bat 'echo Building application...'
            }
        }
        stage('Test') {
            steps {
                bat 'echo Running automated tests...'
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
        stage('Deploy to TEST') {
            when {
                expression {
                    params.ENVIRONMENT == 'TEST'
                }
            }
            steps {
                bat 'echo Deploying application to TEST...'
            }
        }
        stage('Deploy to PROD') {
            when {
                expression {
                    params.ENVIRONMENT == 'PROD'
                }
            }
            steps {
                input message: 'Approve deployment to PROD?',
                      ok: 'Approve'
        
                bat 'echo Deploying application to PROD...'
            }
        }
    }
}
