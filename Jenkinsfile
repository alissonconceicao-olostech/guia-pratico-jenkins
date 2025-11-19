pipeline { 
    agent any

    stages {
        stage ('Build Docker Image') {
            steps {
                //sh 'echo "Executando o comando docker build"'
                script { 
                    dockerapp = docker.build ("alisson.conceicao/guia-jenkins:${env.BUILD_ID}", '-f ./Jenkinsfile' ./'')
                }
            }
        }

      stage ('Push Docker Image') {
            steps {
                //sh 'echo "Executando o comando docker push"'
                script {
                    docker.withRegistry ('https://registry.hub.docker.com', 'dockerhub') {
                        dockerapp.push('latest')
                        dockerapp.push("${env.BUILD_ID}")
                    }
                }
            }
        }

      stage ('Deploy Kubernets') {
            steps {
                sh 'echo "Executando o comando kucebtl apply"'
            }
        }        
    }
}