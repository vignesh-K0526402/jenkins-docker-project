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
		sh 'docker rm -f docsapp-container || true'
                sh 'docker run -d --name docsapp-container -p 8081:80 docsapp'
            }
        }
        stage("System Info"){
            steps{
                sh 'echo "i completed my project on :" '
		sh 'date'
		sh 'echo "current memory in my system :" '
                sh 'free -h'
		sh 'echo "who am i :" '
		sh 'whoami'
		sh  'echo "where am i :" '
		sh 'pwd'
            }
        }
    }
}
