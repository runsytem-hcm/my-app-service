                def mvnHome = tool name: 'maven', type: 'maven'
pipeline {
    agent any 
    stages {
        stage('Build Souce') {
            steps {
                sh "${mvnHome}/bin/mvn clean package" 
            }
        }
    }
}
