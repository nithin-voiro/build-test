pipeline {
    agent any

    environment {
        PATH = "C:\\Windows\\System32;${env.PATH}"
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                bat 'cmd.exe /c echo Building the project using cmd.exe'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'cmd.exe /c echo Running tests using cmd.exe'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                bat 'cmd.exe /c echo Deploying application using cmd.exe'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed.'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed. Check logs for details.'
        }
    }
}
