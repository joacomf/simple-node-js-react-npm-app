pipeline {
    agent none
    environment {
        CI = 'true' 
    }
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:6-alpine' 
                    args '-p 3000:3000' 
                }
            }
            steps {
                sh 'npm install' 
            }
        }
        stage('Test') { 
            agent {
                docker {
                    image 'node:6-alpine' 
                    args '-p 3000:3000' 
                }
            }
            steps {
                sh './jenkins/scripts/test.sh' 
            }
        }
        stage('Deliver') {
            agent {
                docker { 
                    image 'ansible/ubuntu14.04-ansible'
                }
            }
            steps {
                sh './infraestructura/provision.sh ./infraestructura/inventory.demo1'
            }
        }
    }
}
