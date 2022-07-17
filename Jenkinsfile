pipeline {
    agent { label "newslave" }
    stages {
        stage("Build") {
            steps{
                sh 'sudo docker build -t dockerjosealcaraz/cicd-crash-course:latest .'
            }
        }
        stage("Publish") {
            steps{
                withDockerRegistry([credentialsId: "docker-hub", url: ""]) {
                    sh 'sudo docker push dockerjosealcaraz/cicd-crash-course:latest'
                }
            }
        }
    }
}