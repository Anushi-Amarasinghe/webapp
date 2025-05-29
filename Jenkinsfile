pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Code Quality') {
            steps {
                withSonarQubeEnv('My SonarQube Server') {
                sh 'mvn sonar:sonar'
                }
             }
        }

    }
}
