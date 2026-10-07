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
                sh 'docker tag todo-app-cicd "$dockerHubUser/todo-app-cicd:latest"'
                sh 'docker tag todo-app-cicd "$dockerHubUser/todo-app-cicd:$(git rev-parse --short HEAD)"'
                sh 'echo "$dockerHubPass" | docker login -u "$dockerHubUser" --password-stdin'
                sh 'docker push "$dockerHubUser/todo-app-cicd:latest"'
                sh 'docker push "$dockerHubUser/todo-app-cicd:$(git rev-parse --short HEAD)"'
                }
            }
        }
        stage("deploy"){
            steps{
                echo "Deploying the container"
                sh 'export TAG="$(git rev-parse --short HEAD)" && docker-compose down && docker-compose up -d'
            }
        }
    }
}
