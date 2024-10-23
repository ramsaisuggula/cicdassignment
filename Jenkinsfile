pipeline {
    agent any
    tools {
        jdk 'JDK21'
        maven 'maven3'
    }
    stages {
        stage('Build') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/ramsaisuggula/cicdassignment.git']])
                sh 'mvn clean install'
            }
        }
    }
}
