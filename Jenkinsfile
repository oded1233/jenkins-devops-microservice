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
			echo "I'm cool"
		}
		sucess {
			echo "walla"
		}
		failure {
			echo "Baasa"
		}
	}
}
