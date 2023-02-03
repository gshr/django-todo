pipeline {
    agent any 
    stages{
        stage("Checking Docker Version..."){
            steps{
            sh "docker -v"
            echo "docker started"
        }}
        stage("Stop All Running Docker COntainer ..."){
            steps{
                sh 'docker stop \$(docker ps -a -q)'
                echo "stop docker container"
            }
        }
        stage("Remove All  Docker Images"){
            steps{
                sh "docker rm \$(docker ps -a -q)"
                echo "rm docker images"
            }
        }
        stage("Build New Docker image"){
            steps{
                sh "docker build -t demo ."
                echo "Build docker image"
            }
        }
        stage("Run Docker image "){
            steps{
                sh "docker run -d -p 80:80 demo"
                echo "Run docker container"
            }
        }
    }
}