 pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch : 'mastser', url: 'https://github.com/Kumarazdevops/pipeline-ci-cd-18-07.git' 
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
