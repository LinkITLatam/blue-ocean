pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo '"Compilando Codigo del repositorio: ${params.Repositorio}. Usuario: ${GIT_CREDENTIALS_OBJECT_USR}, Password:  ${GIT_CREDENTIALS_OBJECT_PSW}"'
      }
    }
    stage('Test') {
      steps {
        input '"Build Completo! Ejecutar Tests? Se ejecutaran en Paralelo !"'
      }
    }
    stage('Unit Tests') {
      parallel {
        stage('Unit Tests') {
          steps {
            echo 'Los Unit Tests son Maravillosos !'
          }
        }
        stage('Integration Tests') {
          steps {
            echo 'Los Integration Tests son Maravillosos !'
          }
        }
        stage('Smoke Tests') {
          steps {
            echo 'Donde hay humo hay fuego !!'
          }
        }
        stage('Performance Test') {
          steps {
            echo 'No nos olvidemos de la performance ! Ejecutando Tests!'
          }
        }
      }
    }
    stage('CheckPoint') {
      steps {
        checkpoint 'Testing Completo'
      }
    }
    stage('Deploy') {
      steps {
        input 'Esta Seguro que desea generar un deployment ?'
        echo 'Continuamos con el Deployment !'
        echo 'Deployment Completo !'
      }
    }
  }
}