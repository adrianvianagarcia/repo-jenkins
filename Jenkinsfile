pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Clonando repositorio desde GitHub...'
                script {
                    git branch: 'main', 
                        credentialsId: 'github-token', // ID de las credenciales almacenadas en Jenkins
                        url: 'https://github.com/adrianvianagarcia/repo-jenkins.git'
                }
            }
        }
        stage('Install Dependencies') {
            steps {
                echo 'Instalando dependencias...'
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                echo 'Compilando la aplicación React...'
                sh 'npm run build'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Desplegando la aplicación en Apache...'
                sh 'sudo rm -rf /var/www/html/*'
                sh 'sudo cp -r build/* /var/www/html/'
            }
        }
    }
}

