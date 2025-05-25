pipeline {
    agent any

    environment {
        XYZ = 'ITI ITI ITI'
        IMAGE_NAME = 'mariamhossam00/jenkins-sample'
    }

    stages {
        stage("Build Docker Image") {
            steps {
                sh "docker build -t ${IMAGE_NAME}:v${BUILD_NUMBER} ."
            }
        }

        stage("Push Docker Image") {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub-cred', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
                    sh "echo $DOCKER_PASSWORD | docker login -u $DOCKER_USERNAME --password-stdin"
                    sh "docker push ${IMAGE_NAME}:v${BUILD_NUMBER}"
                }
            }
        }
    }
}
