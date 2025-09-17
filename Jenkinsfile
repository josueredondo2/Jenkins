pipeline {
    agent any

    stages {
        stage('Listar Nodos') {
            steps {
                script {
                    import jenkins.model.Jenkins

                    def nodes = Jenkins.instance.nodes
                    echo "=== Lista de Nodos ==="
                    nodes.each { node ->
                        echo "Nombre: ${node.displayName}, NumExecutors: ${node.numExecutors}, Offline: ${node.toComputer().offline}"
                    }
                }
            }
        }
    }
}
