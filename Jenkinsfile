pipeline {
    agent any
    tools {
        jdk 'JDK17'
        maven 'maven3'
    }
    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/ramsaisuggula/cicdassignment.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Docker Build') {
            steps {
                script {
                    docker.build("ramsai914/your-app:${env.BUILD_ID}")
                }
            }
        }
        stage('Push Docker Image') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-credentials-id') {
                        docker.image("ramsai914/your-app:${env.BUILD_ID}").push()
                    }
                }
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker run -d -p 8080:8080 ramsai914/your-app:${env.BUILD_ID}'
            }
        }
    }
}
