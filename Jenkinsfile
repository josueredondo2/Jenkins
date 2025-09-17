pipeline {
    agent any

    stages {
        stage('Listar Nodos') {
            steps {
                script {
                    println "=== Lista de Nodos en Jenkins ==="
                    jenkins.model.Jenkins.instance.nodes.each { nodo ->
                        println "Nombre: ${nodo.displayName}, Descripción: ${nodo.nodeDescription}, Estado: ${nodo.toComputer()?.online ? 'ONLINE' : 'OFFLINE'}"
                    }
                    println "=== Fin de la Lista ==="
                }
            }
        }
    }
}
