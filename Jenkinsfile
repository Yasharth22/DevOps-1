pipeline {
    agent any

    stages {
        stage('Install Node.js') {
            steps {
                echo 'Installing Node.js and npm...'
                sh '''
                    apt update -y
                    apt install -y nodejs npm
                    node -v
                    npm -v
                '''
            }
        }

        stage('Hello World Test') {
            steps {
                echo 'Running Hello World...'
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
