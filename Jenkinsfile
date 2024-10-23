pipeline {
    agent any
    tools {
        jdk 'JDK21'
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
    }
}
