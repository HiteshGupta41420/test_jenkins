pipeline {
    agent {
        dockerContainer {
            image 'docker:dind' // 'docker:dind' or 'docker:latest' with socket mount
            args '-v /var/run/docker.sock:/var/run/docker.sock' // This is the key
        }
    }

    stages {
        stage('Docker Login') {
            steps {
                script {
                    try {
                        withCredentials([usernamePassword(credentialsId: 'docker-cred', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
                            // The DOCKER_USER and DOCKER_PASS environment variables
                            // are now available and safe to use within this block.

                            echo "Attempting to log in to Docker registry..."

                            // Pass the password to Docker via standard input to avoid logging it.
                            sh 'echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin'
                        }
                        echo "Docker login successful."
                    } catch (e) {
                        // The 'catch' block will run if the Docker login command fails.
                        echo "An error occurred during Docker login."
                        echo "Error message: ${e.message}"
                        currentBuild.result = 'FAILURE'
                        error "Pipeline failed due to a Docker login error."
                    }
                }
            }
        }
    }
}