pipeline {
    agent any

    environment {
        // Define environment variables (Optional)
        APP_NAME = 'MyApp'
        DEPLOY_ENV = 'production'
    }

    stages {
        stage('Clone Repository') {
            steps {
                echo 'Cloning the repository...'
                checkout scm // Fetch the code from SCM (Git in this case)
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                bat 'gradlew build' // Replace with your build command
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'gradlew test' // Replace with your test command
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging the application...'
                bat 'gradlew assemble' // Replace with your packaging command
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying ${APP_NAME} to ${DEPLOY_ENV} environment..."
                bat 'deploy_script.bat' // Replace with your deployment command/script
            }
        }
    }

    post {
        always {
            echo 'Cleaning up workspace...'
            deleteDir() // Clean up workspace
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check logs for details.'
        }
    }
}
