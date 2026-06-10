pipeline {
    agent any
    stages{
        stage('Checkout'){
            steps{
                git branch : 'main' , url:'https://github.com/vignesh-K0526402/jenkins-docker-project.git'
            }
        }
        stage("Build Docker Image"){
            steps{
                sh 'docker build -t docsapp .'
            }
        }
        stage("Run Container"){
            steps{
		sh 'docker rm -f docspp-container || true'
                sh 'docker run -d --name docsapp-container -p 8081:80 docsapp'
            }
        }
        stage("System Info"){
            steps{
                sh 'date'
                sh 'memory free -h'
            }
        }
    }
}
