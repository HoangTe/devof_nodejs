pipeline {
    agent any
    stages{
        stage('Clone') {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/HoangTe/devof_nodejs.git'
            }
        }
        stage('Push Docker Hub') {
            steps {
                withDockerRegistry(credentialsId: 'push dockerhub', url:'') 
                {
                    sh label: '', script: 'docker build -t hoangte/t3h-repository .'
                    sh label: '', script: 'docker push hoangte/t3h-repository'
                }
            }
        }
    }
}