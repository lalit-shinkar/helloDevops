pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'backend', url: 'https://github.com/lalit-shinkar/HelloDevOps.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('hellodevops')
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    docker.image('hellodevops').run('-p 5050:5050')
                }
            }
        }
    }
}

