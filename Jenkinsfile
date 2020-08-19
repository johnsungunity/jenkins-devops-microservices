//SCRIPTED


//DECLARATIVE
pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3'} }
	//agent { docker { image 'node:13.8'} }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaved'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Checkout') {
				steps {
					sh 'mvn --version'
					sh 'docker version'
					echo "Build"
					echo "PATH $PATH"
					echo "BUILD NUMBER - $env.BUILD_NUMBER"
					echo "BUILD ID - $env.BUILD_ID"
					echo "$env.JOB_NAME"
				 	echo "$env.BUILD_TAG"					 
				 	echo "URL $env.BUILD_URL"
				}
		}
		stage('Compile') {
				steps {
					sh "mvn clean compile"
					}
		}

		stage('Test') {
				steps {
					sh "mvn test"
				}
		}
		stage('Integration Test') {
				steps {
					sh "mvn failsafe:integration-test failsafe:verify"		
				}
		}


		stage('Package') {
				steps {
					sh "mvn package -DskipTests"		
				}
		}

		stage('Build Docker Image') {
				steps {
					//"docker build -t in28min/currency-exchange-devops:$env.BUILD_TAG"
					script {
						dockerImage = docker.build("johnsungunity/jenkins-devops-microservices:${env.BUILD_TAG}")
					}
				}
		}
		
		stage('Push Docker Image') {
				steps {
					script {
						docker.withRegistry('','jsunity') { 
						dockerImage.push('');
						dockerImage.push('latest');
						}
							}
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
