pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
                    docker {
                        image 'node:18'
                       resuseNode: true
                    }
                }
            steps {
                
                sh '''
                ls -la
                node -v
                npm -v
                npm ci 
                npm run build
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // Add your test steps here
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add your deploy steps here
            }
        }
    }
}