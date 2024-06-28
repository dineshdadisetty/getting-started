pipeline {
    options {
        timeout(time: 1, unit: 'HOURS')
    }
    agent {
        label 'ubuntu-1804 && amd64 && docker'
    }
    stages {
        stage('build and push') {
            when {
                branch 'master'
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
