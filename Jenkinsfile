pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                checkout changelog: false, poll: false, scm: scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Anji399/sbi.git']])
            }
        }
        stage('build') {
            steps {
                bat 'mvn clean install'
            }
        }
        stage('Deploy to Tomcat') {
            steps {
               deploy adapters: [tomcat9(credentialsId: 'tom', path: '', url: 'http://localhost:8085/')], contextPath: 'sbi', onFailure: false, war: '**/*.war' 
            }
        }
    }
}
