pipeline {
    agent any
    stages {
        stage (‘Checkout Repo’){
            steps {
            git branch: ‘main’, url: ‘https://github.com/mexez/Pxx_Php-Todo.git’
        }
        stage('Docker Push') {
            steps {
                echo "Login to DockerHub and push the docker image..."
                withCredentials([usernamePassword(credentialsId: '001', passwordVariable: 'dockerhub001', usernameVariable: 'dockerhub')]){
                    sh "docker login -u ${env.dockerhub} -p ${env.dockerhub001}"
                    echo "Login succeeded......."
                }
            }
        }
    }
}}
