pipeline {
	agent any
	// agent { docker { image 'maven:3.6.3' } }
	// agent { docker { image 'node:21.7.1' } }
	stages {
		stage('Build3') {
			steps {
				echo "Build3"
				// sh 'mvn --version'
				// sh 'node --version'
				echo "PATH - $PATH"
				echo "Build Number - $env.BUILD_NUMBERH"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD.TAG - $env.BUILD.TAG"
				echo "BUILD.URL - $env.BUILD.URL"
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
		changed {
			echo "I run when there was a change from previous build status"
		}
	}
}

