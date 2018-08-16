pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Estamos Compilando !'
      }
    }
    stage('Tests') {
      steps {
        input(message: 'Build Completo! Ejecutar Tests? Se ejecutaran en Paralelo !', ok: 'Ejecutar Tests!')
        echo 'Ejecutando los Tests'
      }
    }
    stage('Unit Tests') {
      parallel {
        stage('Unit Tests') {
          steps {
            echo 'Los Tests Unitarios son muy necesarios!'
          }
        }
        stage('Test de Integración') {
          steps {
            echo 'Si tenemos tests de integracion es aun mejor!'
          }
        }
        stage('Smoke Tests') {
          steps {
            echo 'Donde hay humo, seguro hay fuego!'
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
        input 'Esta Seguro que quiere realizar un deploy?'
        echo 'El codigo se fue a Producción!'
      }
    }
  }
}