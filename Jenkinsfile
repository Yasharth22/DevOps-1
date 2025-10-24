pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Cloning repository...'
                git branch: 'main', url: 'https://github.com/<your-username>/DevOps.git'
            }
        }

        stage('Install Node.js') {
            steps {
                echo 'Installing Node.js and npm...'
                sh '''
                    sudo apt update -y
                    sudo apt install -y nodejs npm
                    node -v
                    npm -v
                '''
            }
        }

        stage('Hello World Test') {
            steps {
                echo 'Creating and running Hello World Node.js app...'
                sh '''
                    echo "console.log('Hello World from Jenkins Node.js Pipeline!')" > hello.js
                    node hello.js
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check logs.'
        }
    }
}
