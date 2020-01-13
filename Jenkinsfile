pipeline {
    agent any 
    stages {
        stage('Clean') { 
            steps {
                bat "mvn clean"
            }
        }
            stage('Package') { 
            steps {
                bat "mvn package"
            }
        }
        stage('Create Image') { 
            steps {
                bat "docker build -t pdppatil/13jan:1.0 . "
            }
        }
        stage('Push Image') { 
             steps {
                withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerHubPwd')]) {
                    bat "docker login -u pdppatil -p ${dockerHubPwd}"
}
                bat "docker push pdppatil/13jan:1.0"
            }
        }
    }
}
