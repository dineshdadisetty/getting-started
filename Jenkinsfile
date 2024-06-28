pipeline {
    agent {
        docker {
            // Use an appropriate Docker image that has Docker installed
            image 'docker:26.1.1'  // Example image with Docker installed
            registryUrl 'https://registry.hub.docker.com'  // Example registry URL
            registryCredentialsId 'dineshdadisetty'  // Credentials for Docker registry
        }
    }
    stages {
        stage('Build and Push') {
            steps {
                sh "docker build -t docker/getting-started ."
                withDockerRegistry([url: "https://registry.hub.docker.com", credentialsId: "docker-hub-credentials"]) {
                    sh "docker push docker/getting-started"
                }
            }
        }
    }
}
