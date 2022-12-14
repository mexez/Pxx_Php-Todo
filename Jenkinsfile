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

                       sh "docker build -t mexy/php-todo:${env.BRANCH_NAME}-${env.BUILD_NUMBER} ."
                }
            }
        }
        stage ('Push Docker Image') {
             steps{
                script {
                         
    // some block 
sh "docker login -u ${env.dockerhub} -p ${env.dockerhub001}"
                    
}

                              
            }
          }
         }

       


  
    }
}
