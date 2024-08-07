pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('With out docker') {
            steps {
                sh '''
                    echo "Without Docker"
                    ls -la
                    touch container-no.txt
                '''
            }
        }
        stage('With docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "With Docker"
                    ls -la
                    touch container-yes.txt
                '''
            }
        }
    }
}
