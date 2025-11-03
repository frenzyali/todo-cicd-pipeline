pipeline {
    agent any
    
    stages{
        stage("Clone Code"){
            steps{
                echo "Cloning the code"
                git url:"https://github.com/frenzyali/todo-cicd-pipeline", branch: "main"
            }
        }
        stage("build"){
            steps{
                echo "Building the code"
                sh "docker build -t todo-app-cicd ."
            }
        }
        stage("push to docker hub"){
            steps{
                echo "Pushing the image to Docker hub"
                withCredentials([usernamePassword(credentialsId:"docker-hub",passwordVariable:"dockerHubPass",usernameVariable:"dockerHubUser")]){
                sh "docker tag todo-app-cicd ${env.dockerHubUser}/todo-app-cicd:latest"    
                sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                sh "docker push ${env.dockerHubUser}/todo-app-cicd:latest"
                }
            }
        }
        stage("deploy"){
            steps{
                echo "Deploying the container"
                sh "docker-compose down && docker-compose up -d"
            }
        }
    }
}
