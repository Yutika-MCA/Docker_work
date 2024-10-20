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
               bat "docker build -t yutika01/fimage ."
            }
        }

        stage('Docker Login') {
            steps {
                bat 'docker login -u "mca.2349@unigoa.ac.in" -p "usingforjenkins" docker.io'
                }
            }
        

        stage('Push Docker Image') {
            steps {
               bat 'docker push yutika01/fimage'
            }
        }

        stage('Run Docker container'){
        steps{
            bat 'docker run -d --name cont1 yutika01/fimage'
        }
        }

        stage('Final message') {
            steps {
                echo 'Running tests...'
            }
        }
        
    }
    
}

    

