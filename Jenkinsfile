                
pipeline {
    agent any 
    tools {
      maven 'maven-3'
    }
    stages {
        stage('Build Souce') {
            steps {
                sh script: 'mvn clean package'
            }
        }
    }
}
