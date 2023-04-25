pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install -DskipTests'
            }
            }
            stage('Deploy') {
            steps {
                ansibleplaybook(inventory:'hosts.ini', playbook:'playbook.yml', installation:ansible)
                }
            }
        }
  }
