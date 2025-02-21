pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Copiando los ficheros'
                sh 'npm install'
                sh 'npm run build'                
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
		echo 'Desploying...'
		sh 'cp -r ./build/* /var/www/html/'    
	    }
        }
    }
}
