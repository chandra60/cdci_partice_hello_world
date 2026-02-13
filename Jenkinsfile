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

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.war'
            }
        }
    }
}

