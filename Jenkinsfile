pipeline {
    agent none

    parameters {
        string(name: 'TARGET_NODE', defaultValue: 'built-in', description: 'Nodo seleccionado automáticamente')
    }

    stages {
        stage('Ejecutar en nodo') {
            agent { label "${params.TARGET_NODE}" }
            steps {
                powershell '''
                    Write-Host "Ejecutando en el nodo seleccionado: $env:COMPUTERNAME"
                '''
            }
        }
    }
}
