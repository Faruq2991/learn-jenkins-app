pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh'''
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    npm run test
                    ls -lart
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Test'
            }
        }
    }
}
