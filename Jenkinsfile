pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/useless-stuff/jen.git'
      }
    }

    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            ws(dir: '/workdir') {
              echo 'hello $BUILD_NUMBER'
            }

          }
        }

        stage('docker api') {
          steps {
            echo 'build api'
          }
        }

        stage('docker broker') {
          steps {
            echo 'docker broker'
          }
        }

        stage('docker job') {
          steps {
            echo 'docker job'
          }
        }

      }
    }

    stage('Tests') {
      parallel {
        stage('Tests') {
          steps {
            sh 'echo "Test!"'
          }
        }

        stage('unit tests') {
          steps {
            echo 'unit test'
          }
        }

        stage('integratio tests') {
          steps {
            echo 'integration tests'
          }
        }

      }
    }

    stage('Terraform') {
      parallel {
        stage('Terraform') {
          steps {
            sh 'echo "Pippo!"'
          }
        }

        stage('build ecs repo') {
          steps {
            echo 'ecs repo'
          }
        }

        stage('containers') {
          steps {
            echo 'push containers'
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploy stage'
          }
        }

        stage('terraform state') {
          steps {
            sh 'echo "Build ${BUILD_NUMBER}"'
          }
        }

        stage('deploy k8s') {
          steps {
            echo 'deploy k8s'
          }
        }

        stage('push to slack') {
          steps {
            echo 'push to slack'
          }
        }

      }
    }

  }
}