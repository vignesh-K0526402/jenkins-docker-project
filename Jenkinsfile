pipeline {
    agent any
    stages{
        stage('Checkout'){
            steps{
                git branch : 'main' , url:""
            }
        }
        stage("Build Docker Image"){
            steps{
                sh 'docker build -t docsp'
            }
        }
        stage("Run Container"){
            steps{
                sh 'docker run -d -p 8081:80 docsapp'
            }
        }
        stage("System Info"){
            steps{
                sh 'echo' ,'date'
                sh 'echo' , 'memory free -h'
            }
        }
    }
}
