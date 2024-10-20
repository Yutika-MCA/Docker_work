pipeline {
    agent any  

    environment {
       PATH="C:\\Program Files\\Docker\\Docker\\resources\\bin;${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
               bat "docker build -t yutika01/Simage ."
            }
        }

        stage('Docker Login') {
            steps {
                bat 'docker login -u "mca.2349@unigoa.ac.in" -p "usingforjenkins" docker.io'
                }
            }
        

        stage('Push Docker Image') {
            steps {
               bat 'docker push yutika01/Simage'
            }
        }

        stage('Run Docker container'){
        steps{
            bat 'docker run -d --name cont2 yutika01/Simage'
        }
        }

        stage('Final message') {
            steps {
                echo 'Running tests...'
            }
        }
        
    }
    
}

    

