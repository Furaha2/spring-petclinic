pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
            }
            stage('Deploy') {
            steps {
                ansible-playbook(inventory:'hosts.ini', playbook:'playbook.yml', installation:ansible)
                }
            }
        }
  }
