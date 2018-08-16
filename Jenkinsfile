pipeline {
  agent any
  stages {
    stage('Deploy OTK Container Stage') {
      parallel {
        stage('Deploy OTK Container 1') {
          steps {
            echo 'deploying otk container 1'
          }
        }
        stage('Deploy OTK Container 2') {
          steps {
            sleep 2
          }
        }
        stage('Deploy OTK Container 3') {
          steps {
            sleep 3
          }
        }
      }
    }
    stage('Fitnesse Test Stage') {
      parallel {
        stage('Fitnesse Smoke Tests') {
          steps {
            sleep(time: 1, unit: 'SECONDS')
          }
        }
        stage('OIDC Tests') {
          steps {
            sleep 2
          }
        }
        stage('OAuth Flow Tests') {
          steps {
            sleep 3
          }
        }
      }
    }
    stage('Restart Container') {
      steps {
        sleep 4
        echo 'Restart Container'
      }
    }
    stage('Scale Up') {
      steps {
        sleep 3
      }
    }
    stage('Scale down') {
      steps {
        sleep 3
      }
    }
  }
}
