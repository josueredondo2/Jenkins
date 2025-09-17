pipeline {
    agent none

    parameters {
        string(name: 'TARGET_NODE', description: 'Nodo seleccionado automáticamente')
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
