pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        ws(dir: '/workdir') {
          echo 'hello'
        }

        sh 'docker ps'
      }
    }

  }
}