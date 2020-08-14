//DECLARATIVE
pipeline {
	agent any
	stages {
		stage('Build') {
				steps {
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
			echo 'always run'
		}
		success {
			echo 'success'
		}
		failure {
			echo 'failure'
		}
	}
}
