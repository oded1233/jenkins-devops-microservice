// Scripted 

node {
	stage('Build1') {
		echo "Build1"
	}
	stage('Test1') {
		echo "Test1"
	}
	stage('Integration-Test1') {
		echo "Integration-Test1"
	}

//declarative

node {
	echo "Build2"
	echo "Test2"
	echo "Integration-Test2"
	}
}

pipeline {
	agent any
	stages {
		stage('Build3') {
			steps {
				echo "Build3"
				echo "Test3"
				echo "Integration-Test3"	
			}
		}
	}
}
