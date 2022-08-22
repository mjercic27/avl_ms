pipeline {
	agent any
	enviroment {
		DOCKERHUB_CREDENTIALS = credentials('mjercic-dockerhub')
	}

	stages {
		stage('Build'){
			steps {
				sh 'docker build -t s1 service1'
			}
		}

		stage('Login'){
			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}

		stage('Push'){
			steps {
				sh 'docker push s1:latest'
			}
		}
	}
	post{
		always{
			sh 'docker logout'
		}
	}
}