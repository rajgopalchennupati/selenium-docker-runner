pipeline{
    agent any
    stages{
        stage("Start Grid"){
            steps{
                sh "docker-compose up -d hub chrome"
            }

        }
        stage("Run Test"){
            steps{
                sh "docker-compose up search-module"
            }
        }

    }
    post {
        always{
            archiveArtifacts artifacts: 'output/**'
            sh "docker-compose down"
        }
    }
}