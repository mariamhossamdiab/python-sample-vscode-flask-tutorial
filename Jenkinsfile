pipeline{
    agent{
        label "java"
    }
    environment{
        XYZ='ITI ITI ITI'
    }
    stages{
        stage("build Docker image"){
            steps{
                sh "docker build -t mariam/itian:v${BUILD_NUMBER} ."
            }
        }
        stage("Push Docker image"){
            steps{
                sh "docker push itiv4/data-iti:v${BUILD_NUMBER}"
            }
        }
    }
}
