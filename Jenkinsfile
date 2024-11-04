pipeline {
    agent { label "mini-project" }


    stages {
        
        
        stage("Code Clone") {
            steps {
                echo "This stage pulls code from my git repository"
                git url: "https://github.com/v-i-k-a-s-1-7/mini-project-ci-cd.git", branch: "main"
                echo "Cloning successful"
            }
        }
        
        stage("Building a Docker Image") {
            steps {
                echo "This stage will build a Docker image"
                sh "docker build -t my-app:latest ."
                echo "Successful building of image"
            }
        }
        
        stage("Push to Docker Hub") {
            steps {
                echo "This is pushing to Docker Hub"
                withCredentials([usernamePassword(credentialsId: 'dockerHubCred',  
                                      passwordVariable: 'dockerHubPass', 
                                      usernameVariable: 'dockerHubUser')]) {
                sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                sh "docker image tag my-app:latest ${env.dockerHubUser}/my-app:latest"
                sh "docker push ${env.dockerHubUser}/my-app:latest"
                echo "image pushed to docker-hub"
                }
            }
        }
        
        stage("Deploy") {
            steps {
                echo "Deployment will be done in this stage"
                sh "docker compose up -d"
            }
        }
    }
}

