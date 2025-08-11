pipeline {
    agent any
    environment {
        DOCKER_USER = credentials('guptahiteshstudy')
        DOCKER_PASS = credentials('h)T-E9/D6CBp?QD')
    }
    stages {
        stage('Docker Login') {
            steps {
                sh """
                echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin
                """
            }
        }
    }
}
