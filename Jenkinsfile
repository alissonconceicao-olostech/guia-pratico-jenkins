pipeline { 
    agent any

    stages {
        stage ('Build Docker Image') {
            steps {
                sh 'echo "Executando o comando docker build"'
            }
        }

      stage ('Push Docker Image') {
            steps {
                sh 'echo "Executando o comando docker push"'
            }
        }
        
      stage ('Deploy Kubernets') {
            steps {
                sh 'echo "Executando o comando kucebtl apply"'
            }
        }        
    }
}