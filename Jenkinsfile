def GIT_BRANCH='master'           
pipeline {
    agent any
    triggers {
        pollSCM('H/2 * * * *')
    }
    tools {
      maven 'maven-3.6.3'
    }
    environment {
        // Docker image versioning
        BUILD_NAME = readMavenPom().getArtifactId()
        BUILD_VERSION = readMavenPom().getVersion()
        IMAGE = "192.168.60.128/cp/${BUILD_NAME}:${BUILD_VERSION}"
        registry = "https://192.168.60.128"
        registryCredential = 'registry-cred'
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
		echo "====== Starting Build Souce ======"
		sh script: 'mvn clean package'
		// sh "${M2_HOME}/mvn clean package"
            }
        }
        stage('Build image') {
            steps {
                echo "====== Starting BUILD IMAGE ======"
                echo "BUILD_NAME: ${BUILD_NAME}"
                echo "BUILD_VERSION: ${BUILD_VERSION}"
                echo "IMAGE: ${IMAGE}"
                script {
                    docker.withRegistry(registry, registryCredential) {
                        def dockerImage = docker.build("${env.IMAGE}")
                        println "Push dockerImage: " + dockerImage
                        dockerImage.push()
                    }
                }
            }
        }
    }
}
def getGitBranch(){
	return scm.branches[0].name
}

