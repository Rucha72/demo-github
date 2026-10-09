pipeline {
    agent any

    stages {
        stage('Use Jenkins Java 21') {
            tools {
                jdk 'JAVA-17'
            }
            steps {
                echo 'Using Jenkins-managed Java'
                bat 'java -version'
                bat 'echo JAVA_HOME=%JAVA_HOME%'
            }
        }

        stage('Use System Java 25') {
            steps {
                echo 'Using system-installed Java'
                bat '"C:\\Program Files\\Java\\jdk-25.0.4\\bin\\java.exe" -version'
            }
        }

        stage('Use Jenkins Java Again') {
            tools {
                jdk 'JAVA-17'
            }
            steps {
                bat 'java -version'
            }
        }
    }
}
