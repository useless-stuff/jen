pipeline {
  agent any
  stages {

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

        stage('integration tests') {
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

        stage('create ecs repos') {
          steps {
            echo 'ecs repo'
          }
        }

        stage('push containers') {
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

        stage('validate terraform state') {
          steps {
            sh 'echo "Build ${BUILD_NUMBER}"'
          }
        }

        stage('deploy k8s') {
          steps {
            echo 'deploy k8s'
          }
        }

      }
    }

    stage('Semantic release') {
      steps {
        echo 'semantic release'
      }
    }

    stage('Push to slack') {
      steps {
        echo 'push to slack'
      }
    }

  }
}