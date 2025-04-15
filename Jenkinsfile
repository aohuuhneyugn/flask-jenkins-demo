pipeline {
    agent any

    stages {
        stage('Clone repo') {
            steps {
                git url: 'https://github.com/aohuuhneyugn/flask-jenkins-demo.git', branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("flask-demo")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    dockerImage.run("-d -p 5000:5000")
                }
            }
        }
    }
}
