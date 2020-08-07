                
pipeline {
    agent any 
    stages {
        stage('Build Souce') {
          def mvnHome = tool name: 'maven', type: 'maven'
            steps {
                sh "${mvnHome}/bin/mvn clean package" 
            }
        }
    }
}
