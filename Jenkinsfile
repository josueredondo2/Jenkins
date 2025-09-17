pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }
    stage('Build') {
      steps {
        sh 'echo Compilando...'
      }
    }
    stage('Test') {
      steps {
        sh 'echo Ejecutando pruebas...'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo Desplegando app...'
      }
    }
  }
}
