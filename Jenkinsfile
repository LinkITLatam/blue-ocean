pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Compilando'
      }
    }
    stage('Test') {
      steps {
        input 'Desea Ejecutar los Tests?'
      }
    }
    stage('Tests Unitarios') {
      parallel {
        stage('Tests Unitarios') {
          steps {
            echo 'Los Tests Unitarios son siempres buenos!'
          }
        }
        stage('Tests de Integracion') {
          steps {
            echo 'Ejecutando tests de Integracion!'
          }
        }
        stage('Smoke Test') {
          steps {
            echo 'Ejecutando Smoke Tests!'
          }
        }
        stage('Test Performance') {
          steps {
            echo 'Performmance Tests'
            echo 'Performmance Tests 2'
          }
        }
      }
    }
    stage('Checkpoint') {
      steps {
        checkpoint 'Testing Completo'
      }
    }
    stage('Deploy') {
      steps {
        input 'Desea hacer el deploy?'
        echo 'Realizando Deploy'
      }
    }
  }
}
