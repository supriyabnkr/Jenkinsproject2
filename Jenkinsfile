pipeline {
    agent any
    environment{
        dockerhub=credentials('dockerhub')
    }
    
    stages {
        stage('Git Checkout....') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'Git', url: 'https://github.com/pravinksavant/jenkins-nodejs-docker-k8s.git']]])
            }
        }
        
        stage('Build Docker Image....') {
            steps {
                sh 'docker build -t pdockersavant/devops-demo:latest . '
            }
        }
        
        
    }
}
