pipeline {
    agent any
    tools {
    jdk 'jdk17'
    maven 'maven'
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
