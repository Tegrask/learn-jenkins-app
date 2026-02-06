pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
                    docker {
                        image 'node:18-alpine'
                       reuseNode true
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
                sh 'test -f build/index.html'
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