pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                echo 'Code cloned from GitHub'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-php-app:v1 .'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'docker rm -f myphpcontainer || true'
            }
        }

        stage('Deploy New Container') {
            steps {
                sh 'docker run -d --name myphpcontainer -p 8082:80 my-php-app:v1'
            }
        }

    }
}
