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
                ansiblePlaybook(inventory:'hosts.ini', playbook:'playbook.yml', installation:'ansible', credentialsId: 'furaha')
                }
            }
        }
}
