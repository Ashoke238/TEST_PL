pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sleep 30
      }
    }
    stage('Code Analysis') {
      steps {
        sleep 45
      }
    }
    stage('Package & Publish') {
      environment {
        Envt = 'Scratch'
      }
      parallel {
        stage('Package & Publish') {
          steps {
            sleep 45
          }
        }
        stage('Share Logs') {
          steps {
            sleep 45
          }
        }
      }
    }
    stage('Deploy Dev') {
      steps {
        sleep 45
      }
    }
    stage('Dev Anlaysis') {
      steps {
        sleep 30
      }
    }
    stage('Dev Gate') {
      steps {
        input 'Approved'
      }
    }
    stage('Deploy QA') {
      environment {
        Envt = 'Scratch'
      }
      parallel {
        stage('Deploy QA') {
          steps {
            sleep 30
          }
        }
        stage('Deploy INT') {
          steps {
            sleep 30
            input 'Int Gate'
          }
        }
        stage('Deploy UAT') {
          steps {
            sleep 30
          }
        }
      }
    }
  }
}