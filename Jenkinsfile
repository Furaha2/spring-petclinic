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
                ansibleplaybook(inventory:'hosts.ini', playbook:'playbook.yml', installation:ansible)
                }
            }
        }
    }
}
