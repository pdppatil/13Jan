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
                
                withCredentials([usernameColonPassword(credentialsId: 'docker', variable: 'docker_test')]) {
                    bat "docker login -u ${docker_test} -p ${docker_test}"
    
}
                bat "docker push pdppatil/13jan:1.0"
            }
        }
    }
}
