
pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'docker build -t photo-album .'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh 'docker run photo-album pytest'  // Добавьте тесты, если они есть.
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    sh 'docker run -d -p 5000:5000 photo-album'
                }
            }
        }
    }
}
