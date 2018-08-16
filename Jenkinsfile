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
  }
  environment {
    GIT_CREDENTIALS_ID = 'gitHub-credentials'
    GIT_CREDENTIALS_OBJECT = 'credentials("${GIT_CREDENTIALS_ID}"'
  }
}