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

        stage('Stop Old Container') {
            steps {
                sh "docker stop docker-jenkins-demo || true"
            }
        }

        stage('Remove Old Container') {
            steps {
                sh "docker rm docker-jenkins-demo || true"
            }
        }

        stage('Docker Container Run') {
            steps {
                sh "docker run -d --name docker-jenkins-demo -p 5001:5001 docker-jenkins-demo:1.0"
            }
        }
    }
}