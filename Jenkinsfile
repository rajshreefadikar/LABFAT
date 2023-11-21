pipeline {
    agent any

    environment {
        // Define environment variables if needed
        MAVEN_HOME = tool 'Maven'
        PATH = "$PATH:$MAVEN_HOME/bin"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                script {
                    def mavenHome = tool 'Maven'
                    sh "${mavenHome}/bin/mvn clean install"
                }
            }
        }


        stage('Deploy') {
            steps {
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
