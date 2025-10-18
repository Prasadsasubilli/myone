pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Pulling code from Git repository...'
                // Correct syntax for Git checkout
                git branch: 'main', url: 'https://github.com/Prasadsasubilli/myone.git'
            }
        }

        stage('Build') {
            steps {
                echo 'No build step required for static HTML project.'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying HTML page to web server directory...'
                // Make sure Jenkins user has permission for /var/www/html
                sh '''
                sudo rm -rf /var/www/html/*
                sudo cp -r * /var/www/html/
                echo "✅ Deployment completed successfully!"
                '''
            }
        }
    }

    post {
        success {
            echo '🎉 Jenkins pipeline finished successfully!'
        }
        failure {
            echo '❌ Jenkins pipeline failed.'
        }
    }
}
