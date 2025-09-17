pipeline {
    agent any

    stages {
        stage('Listar Nodos') {
            steps {
                script {
                    // Esto devuelve los nombres de los nodos que cumplen con el label
                    def nodos = nodesByLabel label: '', offline: false
                    println "=== Nodos en línea ==="
                    nodos.each { println it }
                }
            }
        }
    }
}
