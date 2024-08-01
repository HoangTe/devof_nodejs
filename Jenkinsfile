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
    post {
        always {
            mail bcc: '', body: 'nội dung ', cc: '', from: '', replyTo: '', subject: 'test jenkin', to: 'boy394462@gmail.com'
        }
    }
}