def GIT_BRANCH='master'           
pipeline {
    agent any 

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
	stage('Maven Version') {
            steps {
              echo "====== Maven Version ======: ${env.M2_HOME}"
		sh "${env.M2_HOME}/mvn clean"
            }
        }
    }
}
def getGitBranch(){
	return scm.branches[0].name
}
