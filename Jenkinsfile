pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'my_image:latest'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch : 'main', url: 'https://github.com/Kumarazdevops/pipeline-ci-cd-18-07.git' 
            }
        }
        stage('Docker login'){
            steps{
                bat 'docker login -u sravankumar0338 -p Kumar@1997'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    bat 'docker build -t my_image .'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    bat 'docker run -d --name myimgecont1 -p 8071:80 my_image'
                    bat 'docker volume create vol1'
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
