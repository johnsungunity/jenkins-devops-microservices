//DECLARATIVE
pipeline {
	//agent any
	//agent { docker { image 'maven:3.6.3'} }
	agent { docker { image 'node:13.8'} }
	stages {
		stage('Build') {
				steps {
					sh 'node --version'
					echo "Build"
				}
		}
		stage('Test') {
				steps {
					echo "Test"
				}
		}
		stage('Integrate') {
				steps {
					echo "Build"
				}
		}
			
	}

	post {
		always {
			echo 'I always run'
		}
		success {
			echo 'success'
		}
		failure {
			echo 'failure'
		}
	}
}
