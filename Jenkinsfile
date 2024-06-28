pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout([$class: 'GitSCM', 
                              branches: [[name: '*/main']],
                              userRemoteConfigs: [[url: 'https://github.com/dineshdadisetty/getting-started', credentialsId: 'dineshdadisetty']]])
                }
            }
        }
        // Add more stages as needed
    }
}
