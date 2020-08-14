//DECLARATIVE
pipeline {
	//agent any
	agent {  docker {'maven:3.6.3 '} }
	stages {
		stage('Build') {
				steps {
					sh 'mvn --version'
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
