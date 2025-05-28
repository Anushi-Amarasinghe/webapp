pipeline {
    agent any  // Or specify a specific agent (node)

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'mvnw clean package'  // Or build command
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvnw test'  // Or  test command
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Your deployment steps here (e.g., Docker commands, deployment scripts)
            }
        }
    }
}
