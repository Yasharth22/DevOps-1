pipeline {
    agent any

    stages {
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
