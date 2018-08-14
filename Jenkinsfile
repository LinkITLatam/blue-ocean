pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Estoy Compilando Ahora!'
      }
    }
    stage('Test') {
      steps {
        echo 'Comienza el Testing !'
      }
    }
    stage('Unit Testing') {
      parallel {
        stage('Unit Testing') {
          steps {
            echo 'Unit Testing Done!'
          }
        }
        stage('Integration Testing') {
          steps {
            echo 'Integration Testing Done!'
          }
        }
        stage('Smoke Testing') {
          steps {
            echo 'Smoke Testing Done!'
          }
        }
      }
    }
    stage('Checkpoint') {
      steps {
        checkpoint 'Checkpoint'
      }
    }
    stage('Deploy') {
      steps {
        input(message: 'Desea Realizar un Deploy?', id: 'deploy', ok: 'Iniciar Deploy')
        echo 'Comenzamos con el Deploy!'
        echo 'Deploy Finalizado'
      }
    }
  }
}
