pipeline {
    agent any
    tools {
        jdk 'JDK17'
    }
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
                //soonar code
                withSonarQubeEnv('My SonarQube Server') {
                sh 'mvn sonar:sonar'
                }
             }
        }

    }
}
