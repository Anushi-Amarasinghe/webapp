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
                withSonarQubeEnv('My SonarQube Server') {
                    sh 'mvn sonar:sonar'
                }
            }
        }
        stage('Security') {
            steps {
                dependencyCheck additionalArguments: '''
                    --scan .
                    --out .
                    --format ALL
                    --prettyPrint
                ''', odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
                dependencyCheckPublisher pattern: 'dependency-check-report.xml'
            }
        }
        stage('Test') {
            steps {
                 sh 'mvn test'
             }
        }
        stage('Code Coverage') {
            steps {
                jacoco execPattern: 'target/jacoco.exec'
            }
        }


    }
}
