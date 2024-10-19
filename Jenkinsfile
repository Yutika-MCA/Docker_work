pipeline {
    agent any  

    environment {
       PATH="C:/Program Files/Docker/Docker/resources/bin:${env.PATH}"
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
                script {
                    echo 'Building Docker image...'
                    // Build the Docker image
                    sh 'docker build -t Yutika-MCA/Docker_work .'
                }
            }
        }

        stage('Docker Login') {
            steps {
                bat 'docker login -u "mca.2349@unigoa.ac.in" -p "usingforjenkins" docker.io'
                }
            }
        

        stage('Push Docker Image') {
            steps {
               bat 'docker push yutika01/first'
            }
        }
    }
    
}

    

