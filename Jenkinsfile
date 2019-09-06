pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3037:3037' 
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
