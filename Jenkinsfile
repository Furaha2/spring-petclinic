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

        stage('SonarQube Analysis') {
            environment {
                scannerHome = tool 'SonarQube Scanner'
            }
            steps {
                withSonarQubeEnv('sonarserver') {
                    sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=develop"
                }
            }
        }
    }
}
