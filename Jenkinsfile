pipeline {
    options {
        timeout(time: 1, unit: 'HOURS')
    }
    agent {
        label 'ubuntu-1804 && amd64 && docker'
    }
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
        stage('Build and Push') {
            when {
                branch 'main'
            }
            steps {
                sh "docker build -t docker/getting-started ."
                withDockerRegistry([url: "", credentialsId: "dineshdadisetty"]) {
                    sh "docker push docker/getting-started"
                }
            }
        }
    }
}
