pipeline {
    options {
        timeout(time: 1, unit: 'HOURS')
    }
    agent {
        label 'docker'
    }
    stages {
        stage('build and push') {
           
            steps {
                sh "docker build -t docker/getting-started ."
                withDockerRegistry([url: "", credentialsId: "dineshdadisetty"]) {
                    sh "docker push docker/getting-started"
                }
            }
        }
    }
}
