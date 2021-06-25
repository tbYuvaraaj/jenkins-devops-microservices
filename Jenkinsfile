// Scripted pipeline

/* node {
	stage('Build') {
		echo "Build"
	}
	stage('Test') {
		echo "Test"
	}
	stage('Integration Test') {
		echo "Integration Test"
	}
	
} */

// Declarative pipeline

pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				echo "Build Process"
			}
		}

				stage('Test') {
			steps {
				echo "Test process"
			}
		}

				stage('Integration test') {
			steps {
				echo "Integration test completed"
			}
		}
	}
}
