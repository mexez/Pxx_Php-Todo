pipeline {
    agent any

    stages {

        stage('Initial Cleanup') {
            steps {
            dir("${WORKSPACE}") {
              deleteDir()
            }
          }
        }

        stage ('Checkout Repo'){
            steps {
            git branch: 'main', url: 'https://github.com/mexez/Pxx_Php-Todo.git'
      }
        }

        stage ('Build Docker Image') {
            steps {
                script {

                       sh "docker build -t nerd2021/php-todo:${env.BRANCH_NAME}-${env.BUILD_NUMBER} ."
                }
            }
        }
        stage ('Push Docker Image') {
             steps{
                script {
            sh "docker login -u ${env.username} -p ${env.password}"

            sh "docker push nerd2021/php-todo:${env.BRANCH_NAME}-${env.BUILD_NUMBER}"
                    
            
            }
          }
         }

       

  
    }
}
