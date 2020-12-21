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

    stage('Tests') {
      steps {
        sh 'echo "Test!"'
      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploy stage'
          }
        }

        stage('') {
          steps {
            sh 'echo "Build ${BUILD_NUMBER}"'
          }
        }

      }
    }

  }
}