pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Cloning repository...'
                checkout scm // Uses the repository configured in the Jenkins job
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                bat '''
                    echo Starting Build Process
                    dir
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat '''
                    echo Running Test Cases
                    dir
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                bat '''
                    echo Deployment Step
                    dir
                '''
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
