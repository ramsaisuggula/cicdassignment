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
                sh 'echo $JAVA_HOME'
                sh 'mvn clean install'
            }
        }
    }
}
