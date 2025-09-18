pipeline {
    agent none

    parameters {
        choice(
            name: 'TARGET_NODE',
            choices: ['Controlador', 'OtroNodox'],
            description: 'Nodo donde ejecutar el query en SQL Server'
        )
    }

    environment {
        DB_CREDENTIALS = credentials('sqlserver-cred-id')
    }

    stages {
        stage('Checkout') {
            // Siempre en el nodo central (master/controller)
            agent { label 'built-in' }
            steps {
                checkout scm
            }
        }

        stage('Ejecutar query en SQL Server') {
            agent { label "${params.TARGET_NODE}" }
            steps {
                powershell '''
                    Write-Host "Ejecutando query en el nodo: $env:COMPUTERNAME"

                    $SqlServer = "localhost"
                    $Database = "master"
                    $User = "${env.DB_CREDENTIALS_USR}"
                    $Password = "${env.DB_CREDENTIALS_PSW}"

                    # Query de prueba
                    $Query = "SELECT HOST_NAME();"

                    sqlcmd -S $SqlServer -d $Database -U $User -P $Password -Q $Query
                '''
            }
        }
    }
}
