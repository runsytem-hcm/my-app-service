def GIT_BRANCH='master'           
pipeline {
    agent any 
    tools {
      maven 'maven-3.6.3'
    }
    stages {
        stage('Checkout Source Code') {
            steps {
                echo "====== Starting CHECKOUT SOURCE CODE ======"
	        script {
		   GIT_BRANCH = getGitBranch()
		}
		echo "Checkout branch: ${GIT_BRANCH}"
                checkout scm
          }
        }
        stage('Build Souce') {
            steps {
                sh script: 'mvn clean package'
            }
        }
    }
}
def getGitBranch(){
	return scm.branches[0].name
}
