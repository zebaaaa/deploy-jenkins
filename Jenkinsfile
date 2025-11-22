pipeline {
    agent any 
    stages{
        stage('install nginx'){
            steps{
                sh 
                '''
                sudo apt update -y 
                sudo apt install nginx -y
                '''
            }
        }
        stage('deploy custom index page'){
            steps{
                sh
                '''
                sudo rm -f /var/www/html/index.nginx-debian.html
                sudo cp index.html /var/www/html/index.html
                sudo systemctl restart nginx 
                '''
            }

        }
    }
}