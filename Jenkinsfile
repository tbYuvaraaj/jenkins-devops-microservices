// Scripted pipeline. Git poll won't work in scripted style

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

// Declarative pipeline. Git poll will work here

pipeline {
	agent any
	//agent {docker {image 'maven:3.8.1'}}
	stages {
		stage('Build') {
			steps {
				//sh 'mvn --version'
				echo "Build Process"
				echo "Branch Name: $env.BRANCH_NAME"
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
