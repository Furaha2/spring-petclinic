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

        stage('Ansible Playbook') {
            environment {
                scannerHome = tool 'SonarQube Scanner'
            }
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
