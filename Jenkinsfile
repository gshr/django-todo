pipeline {
    agent any 
    stages{
        stage("Docker build"){
            steps{
            sh "docker -v"
            echo "docker started"
        }}
        stage("Stop Docker"){
            steps{
                sh "docker stop $(docker ps -a -q)"
                echo "stop docker container"
            }
        }
        stage("Remove Docker Images"){
            steps{
                sh "docker rm $(docker ps -a -q)"
                echo "rm docker images"
            }
        }
        stage("Build Docker"){
            steps{
                sh "docker build -t demo ."
                echo "Build docker image"
            }
        }
        stage("Run Docker"){
            steps{
                sh "docker run -d -p 80:80 demo"
                echo "Run docker container"
            }
        }
    }
}