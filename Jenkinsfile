pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/damiguet/jenkins.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Compilando proyecto...'
                sh 'echo "Hola desde Jenkins!" > resultado.txt'
            }
        }

        stage('Test') {
            steps {
                echo 'Ejecutando tests...'
                sh 'echo "Test OK"'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'resultado.txt', onlyIfSuccessful: true
        }
    }
}
