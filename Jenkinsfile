pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Will use the repo + credentials from job config
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo "Building the application..."
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying the application..."
            }
        }
    }
}
