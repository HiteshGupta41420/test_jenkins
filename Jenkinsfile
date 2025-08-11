pipeline {
    agent any
    environment {
        DOCKER_USER = credentials("guptahiteshstudy")
        DOCKER_PASS = credentials("h)T-E9/D6CBp?QD")
    }
    stages {
        stage('Docker Login') {
            steps{
                script {
                    try{
                        echo $DOCKER_USER
                        echo $DOCKER_PASS
                        echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin
                    } catch (e){
                        echo "An error occured"
                        echo "Error message: ${e.message}" 
                    }
                }
            }
        }
    }
}
