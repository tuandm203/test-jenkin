pipeline {
    agent any
    stages {
        stage ('Clone stage') {
            steps {
                git branch: 'main', url: 'https://github.com/tuandm203/test-jenkin.git'
            }
        }

        stage ('Build stage') {
            steps {
                withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
                    sh 'docker build -t tuan1102003/web-jenkins-demo .'
                    sh 'docker push tuan1102003/web-jenkins-demo'
                }
            }
        }
    }
}