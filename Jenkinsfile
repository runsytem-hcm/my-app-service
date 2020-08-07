                
pipeline {
    agent any 
  environment{
    PATH = "/opt/apache-maven-3.6.3/bin:$PATH"
  }
    stages {
        stage('Build Souce') {
            steps {
                sh "mvn clean package" 
            }
        }
    }
}
