pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/manishbad/pythonproject.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -t python-hello-app ."
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh "docker run -itd -p 5000:5000 python-hello-app"
                }
            }
        }
    }
}
