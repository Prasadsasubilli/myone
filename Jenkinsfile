pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Pulling code from Git repository...'
                checkout scm
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
                // Adjust path as needed (e.g., /usr/share/nginx/html if using Nginx)
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
