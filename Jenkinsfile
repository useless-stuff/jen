pipeline {
  agent any
  stages {

    stage("Checkout") {
            steps {
                git url: 'https://github.com/useless-stuff/jen.git'
        }
    }

    stage('Build') {
      steps {
        ws(dir: '/workdir') {
          echo 'hello $BUILD_NUMBER'
        }

      }
    }

    stage('Tests') {
      steps {
        sh 'echo "Test!"'
      }
    }

    stage('Pippo') {
          steps {
            sh 'echo "Pippo!"'
          }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploy stage'
          }
        }

        stage('Validate terraform state') {
          steps {
            sh 'echo "Build ${BUILD_NUMBER}"'
          }
        }

      }
    }

  }
}