pipeline {
    agent any
    tools {
        maven 'Maven'
            }
    stages {
        stage('Build') {
            steps {
                sh 'mvnw clean package'
            }
        }

        stage('Deploy') {
            
            steps {
                ansibleplaybook(inventory:'hosts.ini', playbook:'playbook.yml', installation:'ansible', credentialsId: 'furaha')
                }
            }
        }
}
