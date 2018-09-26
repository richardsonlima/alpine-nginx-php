pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t richardsonlima/alpine-nginx-php:${env.BUILD_ID} .'
            }
        }
        stage('Push to dockerhub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
                sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
                sh 'docker push richardsonlima/alpine-nginx-php:${env.BUILD_ID}'
            }
         }
      }
   }
}
