pipeline {
    agent any

    stages {
        stage('Instalar Dependências') {
            steps {
                echo 'Instalando dependências do projeto...'
                bat 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo 'Executando o Build do projeto...'
                bat 'npm run build --if-present'
            }
        }

        stage('Testes') {
            steps {
                echo 'Executando os testes unitários...'
                bat 'npm test'
            }
        }
    }

    post {
        success {
            echo '==================================================='
            echo ' SUCCESS: O pipeline foi executado com sucesso!'
            echo '==================================================='
        }
        failure {
            echo '==================================================='
            echo ' FAILURE: Houve uma falha na execução do pipeline.'
            echo '==================================================='
        }
        always {
            echo 'Limpando o ambiente/Concluindo execução.'
        }
    }
}
