pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Asadmahmand/test1.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('python5')
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    def app = docker.image('python5')
                    app.run('-p 86:80')
                }
            }
        }
    }
}
