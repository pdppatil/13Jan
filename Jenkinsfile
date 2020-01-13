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
    }
}
