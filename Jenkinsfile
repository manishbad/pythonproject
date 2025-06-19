pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/manishbad/pythonproject.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('python-hello-app')
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    docker.image('python-hello-app').run('-p 5000:5000')
                }
            }
        }
    }
}

