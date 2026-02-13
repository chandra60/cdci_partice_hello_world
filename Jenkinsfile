pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Build WAR') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t hello-app .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker rm -f hello-container || true
                docker run -d -p 8081:8080 --name hello-container hello-app
                '''
            }
        }
    }
}

