pipeline {
	agent any
	stages {
		stage('Build3') {
			steps {
				echo "Build3"
			}
		}
		stage('Test3') {
			steps {
				echo "Test3"
			}
		}	
		stage ('Integration-Test3') {
			steps {
				echo "Integration-Test3"
		    }
		}
	} 

	post {
		always {
			echo "I'm always cool"
		}
		success {
			echo "walla, I am a sucess"
		}
		failure {
			echo "Baasa, something went wrong"
		}
		// changed {
			echo "I run when there was a change from previous build status"
		}
	}
}
