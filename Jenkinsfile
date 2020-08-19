//DECLARATIVE
pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3'} }
	//agent { docker { image 'node:13.8'} }
	stages {
		stage('Build') {
				steps {
					//sh 'node --version'
					echo "Build"
					echo "PATH $PATH"
					echo "BUILD NUMBER - $env.BUILD_NUMBER"
					echo "BUILD ID - $env.BUILD_ID"
					echo "$env.JOB_NAME"
				 	echo "$env.BUILD_TAG"					 
				 	echo "URL $env.BUILD_URL"
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
