pipeline {
    agent any
    tools {
        maven 'Maven'
            }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                ansible --version
                ansible-playbook --version
                ansible-galaxy --version
                '''
                }
            }
        }
    }
}
