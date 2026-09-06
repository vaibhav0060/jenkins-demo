pipeline {
	agent any

	stages {
		stage('Hello World') {
			steps {
				echo 'Hello World'
			}
		}
        stage('success') {
			steps {
				echo 'pipeline successful'
			}
		}
        stage('Docker Build') {
			steps {
				sh "docker build -t docker-jenkins-demo:1.0 ."
			}
		}
        stage('Docker container Run ') {
			steps {
				sh "docker run -d -p 5001:5001 docker-jenkins-demo:1.0"
			}
		}
	}
}
