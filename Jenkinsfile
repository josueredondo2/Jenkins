pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                powershell 'echo Hola desde Windows'
            }
        }
        stage('Test') {
            steps {
                powershell 'Write-Host "Ejecutando pruebas..."'
            }
        }
    }
}
