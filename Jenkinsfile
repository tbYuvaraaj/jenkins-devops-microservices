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
	environment {
		dockerHome = tool 'MyMaven'
		mavenHome = tool 'MyDocker'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Build') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build Process"
			}
		}

		stage('Compile') {
			steps {
				echo "Compile step started...."
				sh "mvn clean compile"
			}
		}

		stage('Test') {
			steps {
				echo "Test started...."
				sh "mvn test"
			}
		}

		stage('Package') {
			steps {
				sh "mvn package -DskipTests"
			}
		}



		stage('Build docker image') {
			steps {
				script {
					dockerImage = docker.build("tbyuvaraaj/fromdocker:0.0.2.RELEASE")
				}
			}
		}

		stage('Push Docker image') {
			steps {
				script {
					docker.withRegistry('','DockerHub') {
					dockerImage.push();

					}

				}
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
