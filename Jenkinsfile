pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3006:3006' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
    }
}