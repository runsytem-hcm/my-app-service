pipeline {
    agent any 
    stages {
        stage('Build Souce') {
            steps {
                def mvnHome = tool name: 'maven', type: 'maven'
                sh "${mvnHome}/bin/mvn clean package" 
            }
        }
    }
}
