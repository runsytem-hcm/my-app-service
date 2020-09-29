def GIT_BRANCH='master'           
pipeline {
    agent any 
    environment{
     PATH = "/opt/apache-maven-3.6.3/bin:$PATH"
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
	stage('Maven Version') {
            steps {
              echo "====== Maven Version ======"
		sh script: 'mvn clean package'
            }
        }
    }
}
def getGitBranch(){
	return scm.branches[0].name
}
