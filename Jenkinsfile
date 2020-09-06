pipeline {
    agent any
    stages {
        stage('Create docker image') {
            steps {
                script {
                    echo 'Create Dockerfile ...'
                    sh 'docker build -t http://registry-192.168.1.38.nip.io/homeassistant/raspberrypi3-homeassistant-ci:latest .'
                }
            }
        }
        stage('Push docker image') {
            steps {
                script {
                    echo 'Push Docker Image ...'
                    sh 'docker push registry-192.168.1.38.nip.io/homeassistant/raspberrypi3-homeassistant-ci:latest'
                }
            }
        }

    }
    post {
        always {
            cleanWs()
        }
    }
}