pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Get the latest code from the Git repository
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Build the Maven project
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Run tests (replace this with your actual test command)
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                // Add deployment steps (if applicable)
                echo 'Deployment steps go here'
            }
        }
    }

    post {
        success {
            // Actions to perform if the pipeline succeeds
            echo 'Pipeline succeeded!'
        }
        failure {
            // Actions to perform if the pipeline fails
            echo 'Pipeline failed!'
        }
    }
}
