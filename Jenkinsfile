pipeline {
    agent any
    
    environment {
        registryCredentials = credentials('dineshdadisetty')  // Credential ID for Docker registry
        dockerImage = 'docker:20.10.9'  // Example Docker image with Docker CLI installed
    }

    stages {
        stage('Build and Push') {
            steps {
                script {
                    // Pull Docker image (optional, if needed)
                    sh "docker pull $dockerImage"
                    
                    // Build Docker image
                    sh "docker build -t docker/getting-started ."
                    
                    // Push Docker image to registry
                    withDockerRegistry(credentialsId: registryCredentials, url: "https://registry.hub.docker.com") {
                        sh "docker push docker/getting-started"
                    }
                }
            }
        }
    }
}
