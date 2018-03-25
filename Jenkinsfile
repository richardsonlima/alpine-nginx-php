  pipeline {
  agent {
    docker 'bpmd-alpine-nginx:latest'
  }
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        sh 'sudo docker run -d -p 80:80 richardsonlima/bpmd-alpine-nginx:latest'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing..'
        sh 'nc -v localhost 80'
      }
    }
  }
}
