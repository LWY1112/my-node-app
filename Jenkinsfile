pipeline {
    agent any

    tools {
        nodejs 'nodejs' // Ensure this matches the NodeJS installation name in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/LWY1112/my-node-app.git', branch: 'main'
            }
        }

        stage('Install dependencies') {
            steps {
                bat 'npm install' // Use 'bat' instead of 'sh' for Windows compatibility
            }
        }

        stage('Run tests') {
            steps {
                bat 'npm test' // Use 'bat' instead of 'sh' for Windows compatibility
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
