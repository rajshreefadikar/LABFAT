pipeline {
    agent any
    tools {
        maven 'Maven'
    }
    stages {
        stage('Clone Code') 
        {
            steps {
                git 'https://github.com/rajshreefadikar/LABFAT.git'
                echo 'Data Clone Successfully'
            }
        }
         stage('Build Project') 
        {
            steps {
                bat 'mvn install'
                echo 'Data Clone Successfully'
            }
        }
        
    
    stage('Build Docker Image') {
    steps {
        script {
            def dockerImage = 'labfat:latest'

            // Use the 'bat' step for Windows batch commands
            def dockerBuildCmd = "docker build -t ${dockerImage} ."

            
        }
    }
}

    
    stage('Push Docker Image') {
            steps {
                // Push Docker image to a central repository
                script {
                    def dockerImage = 'labfat:latest'
                    def registryUrl = 'https://hub.docker.com/repository/docker/rajshree/LABFAT/general'

                    
                    
                    
                    withCredentials([usernamePassword(credentialsId: 'DockerID', passwordVariable: 'rajshree123', usernameVariable: 'rajshree')]) {
    

    bat """docker login -u "${usernameVariable}" -p "${passwordVariable}" ${registryUrl}"""
    bat """docker push ${dockerImage}"""
}
                }

}
}
        stage('Handle Errors') {
            steps {
                script {
                    currentBuild.result = 'FAILURE'
                    echo 'Error: The pipeline has encountered a failure.'
                }

}
}
}

triggers{
            cron('H/5 * * * *')
    
}

}
