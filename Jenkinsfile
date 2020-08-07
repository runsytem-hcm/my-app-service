pipeline {
    agent any 
    stages {
        stage('Build Souce') {
            steps {
                sh "${env.M2}/mvn clean package" 
            }
        }
    }
}
