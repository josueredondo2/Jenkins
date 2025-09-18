pipeline {
    agent none

    parameters {
        choice(
            name: 'TARGET_NODE',
            choices: ['built-in', 'ServidorRemoto', 'Controlador'],
            description: 'Selecciona el nodo donde ejecutar el query'
        )
    }

    environment {
        // ID de las credenciales almacenadas en Jenkins
        DB_CREDENTIALS = credentials('sqlserver-cred-id')  
    }

    stages {
        stage('Ejecutar query en SQL Server') {
            agent { label "${params.TARGET_NODE}" }
            steps {
                powershell '''
                    Write-Host "Ejecutando query en el nodo: $env:COMPUTERNAME"

                    # Datos de conexión
                    $SqlServer = "localhost"
                    $Database = "master"
                    $User = "${env.DB_CREDENTIALS_USR}"
                    $Password = "${env.DB_CREDENTIALS_PSW}"

                    # Query a ejecutar
                    $Query = "SELECT HOST_NAME();"

                    # Ejecutar con sqlcmd
                    sqlcmd -S $SqlServer -d $Database -U $User -P $Password -Q $Query
                '''
            }
        }
    }
}
