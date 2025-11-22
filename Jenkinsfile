pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                // Simple git pull
                git branch: 'main',
                    url: 'https://github.com/zebaaaa/deploy-jenkins.git'
            }
        }

        stage('Install Nginx') {
            steps {
                sh '''
                    sudo apt update -y
                    sudo apt install nginx -y
                '''
            }
        }

        stage('Deploy Custom Index Page') {
            steps {
                sh '''
                    sudo rm -f /var/www/html/index.nginx-debian.html
                    sudo cp index.html /var/www/html/index.html
                    sudo systemctl restart nginx
                '''
            }
        }
    }
}
