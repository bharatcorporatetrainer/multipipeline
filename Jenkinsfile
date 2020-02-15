pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 4000:3000 -p 7000:5000'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
               echo "I am in build stage"
            }
        }
        stage('Test') {
            steps {
               echo "Unit tests are being executed"
            }
        }
        stage('Deliver for development') {
            when {
                branch 'development' 
            }
            steps {
                echo "development branch executed successfully"
            }
        }
        stage('Deploy for production') {
            when {
                branch2 'production'  
            }
            steps {
                echo "production branch executed successfully"
            }
        }
    }
}
