pipeline {
    agent any
    stages {
        stage('Clone the Code') {
            steps {
                echo "Cloning the code"
                git branch: 'main', url: 'https://github.com/Potharaj-Pavan/django-notes-app.git'
            }
        }
        stage('Build the Image') {
            steps {
                echo "Building the Image"
                sh '''docker build -t notes-app .'''
            }
        }
        stage('Push the Image to DockerHub') {
            steps {
                echo "Pushing the Image to DockerHub"
                withCredentials([usernamePassword(credentialsId:"DockerHub",passwordVariable:"DockerHubPass",usernameVariable:"DockerHubUser")]) {
                sh "docker tag notes-app  ${env.DockerHubUser}/notes-app:latest"
                sh "docker login -u ${env.DockerHubUser} -p ${env.DockerHubPass}"
                sh "docker push ${env.DockerHubUser}/notes-app:latest"
                }
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying the Container"
                sh"docker-compose down && docker-compose up -d"
            }
        }
    }
}
