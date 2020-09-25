                
pipeline {
    agent any 

    stages {
        stage('Build Souce') {
            steps {
              echo "====== Starting BUILD SOURCE ======"
              sh "${env.M2_HOME}/mvn clean package"
            }
        }
    }
}
