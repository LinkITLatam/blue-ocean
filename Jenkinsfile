pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building'
      }
    }
    stage('Tests') {
      steps {
        input 'Do you really want to test?'
      }
    }
    stage('Unit Tsts') {
      parallel {
        stage('Unit Tsts') {
          steps {
            echo 'Executing Unit Testing'
          }
        }
        stage('Performance Testing') {
          steps {
            echo 'Executing unit testing'
          }
        }
        stage('Smoke Test') {
          steps {
            echo 'smoke tests done!'
          }
        }
      }
    }
    stage('Checkpoint') {
      steps {
        checkpoint 'Testing Completed'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploy done'
        input 'Do you really want to do a deploy?'
      }
    }
  }
}