pipeline {
  agent any

  stages {
    stage('Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[
                        url: 'https://github.com/HiteshGupta41420/test-jenkins.git',
                        credentialsId: 'GitCred'
                    ]]
                ])
            }
    }
    stage('Build') {
      steps {
        echo 'Building the app...'
      }
    }
    stage('Test') {
      steps {
        echo 'Running tests...'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying...'
      }
    }
  }
}
