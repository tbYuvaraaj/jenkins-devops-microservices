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

	post {
		always {
			echo "This will be executed always"
		}

		success {
			echo "This will be executed on success"
		}

		failure {
			echo "This will be executed on failure"
		}
	}
}
