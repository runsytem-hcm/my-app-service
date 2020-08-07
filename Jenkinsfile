                
pipeline {
    agent any 
            def mvnHome = tool name: 'maven', type: 'maven'
    stages {
        stage('Build Souce') {
            steps {
                sh "${mvnHome}/bin/mvn clean package" 
            }
        }
    }
}
