pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Compilando!'
      }
    }
    stage('Tests') {
      steps {
        input 'Desea Correr los tests?'
      }
    }
    stage('Tests Unitarios') {
      parallel {
        stage('Tests Unitarios') {
          steps {
            echo 'Siempre es bueno tener tests unitarios!'
          }
        }
        stage('Tests de Integracion') {
          steps {
            echo 'Los Test de intergracion son aun mejores!'
          }
        }
        stage('Smoke Tests') {
          steps {
            echo 'Donde hay humo, hay fuego!'
          }
        }
        stage('Performance Tests') {
          steps {
            echo 'Ahora si estamos completos!'
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
        input 'Desea realizar el Deploy?'
        echo 'Ejecutando Deploy!'
      }
    }
  }
}