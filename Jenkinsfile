pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', credentialsId: '                        credentialsId: 'GitCred', url: 'https://github.com/HiteshGupta41420/test_jenkins.git'
                // NOTE: 'credentialsId' is needed if your repo is private.
                // For a public repo, you can omit 'credentialsId' and 'credentials:' parameter above.
                // If you use a public repo, ensure the URL is also public.
                // You might need to set up a 'Username with password' credential in Jenkins for your GitHub account.
            }
        }
        stage('Install Dependencies') {
            steps {
                echo 'Installing Python dependencies...'
                sh 'pip install -r ./my-app/requirements.txt'
            }
        }
        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                sh 'pytest' // Or 'python -m unittest discover' or similar
            }
        }
    }
    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Build successful!!! 🎉'
        }
        failure {
            echo 'Build failed! ❌ Check the console output for details.'
            // You could add email notifications here later
        }
    }
}