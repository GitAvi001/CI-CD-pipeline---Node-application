pipeline {
    agent any 
    
    stages { 
        stage('SCM Checkout') {
            steps {
                retry(3) {
                    git branch: 'main', url: 'https://github.com/GitAvi001/CI-CD-pipeline---Node-application'
                }
            }
        }
        stage('Build Docker Image') {
            steps {  
                bat 'docker build -t avindudocker1/nodeapp-demo:%BUILD_NUMBER% .'
            }
        }
        stage('Login to Docker Hub') {
            steps {
                withCredentials([string(credentialsId: 'dockerhub-password-test', variable: 'dockerhub-pwd-test')]) {
                    script {
                        bat "docker login -u avindudocker1 -p %dockerhub-pwd-test%"
                    }
                }
            }
        }
        stage('Push Image') {
            steps {
                bat 'docker push avindudocker1/nodeapp-demo:%BUILD_NUMBER%'
            }
        }
    }
    post {
        always {
            bat 'docker logout'
        }
    }
}

