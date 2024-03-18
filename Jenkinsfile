pipeline {
	agent any
	// agent { docker { image 'maven:3.6.3' } }
	// agent { docker { image 'maven:3.9.6' } }
	// agent { docker { image 'node:21.7.1' } }
	environment {
		dockerHome = tool 'mydocker'
		mavenHome = tool 'mymaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Checkout') {
			steps {
				echo "checkout"
				sh 'mvn --version'
				// sh 'node --version'
				sh 'docker version'
				echo "PATH - $PATH"
				echo "Build Number - $env.BUILD_NUMBERH"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "TAG_NAME - $env.TAG_NAME"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}			
		stage('Compile') {
			steps {
				echo "Compile"
				sh 'mvn clean compile'
			}
		}
		// stage('Test') {
		// 	steps {
		// 		echo "Test"
		// 		sh 'mvn test'
		// 	}
		// }	
		// stage ('Integration-Test') {
		// 	steps {
		// 		echo "Integration-Test"
		// 		sh 'mvn failsafe:integration-test failsafe:verify'
		//     }
		// }
		stage ('package') {
			steps {
				echo "package"
				sh 'mvn package -DskipTests'
		
		
		stage ('Build Docker Image') {
			steps {
				echo "Build Docker Image"
				// docker build -t oded1233/currency-exchange-devops:$env.BUILD_ID
				script {
					dockerImage = docker.build("oded1233/currency-exchange-devops:${$env.BUILD_ID}")
				}
			}
		}
		stage ('Push Docker Image') {
			steps {
				echo "Push Docker Image"
				script {
					docker.withRegistry('','dockerhub') {
						dockerImage.push();
						dockerImage.push('latest');
					}
				}
				
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