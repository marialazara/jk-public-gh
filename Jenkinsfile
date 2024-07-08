pipeline {
    agent any

    stages {
        stage('Cloning GIT Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/marialazara/jk-public-gh.git'
            }
        }
        
        stage('Build Docker Image') {
            steps {
               sh "docker build -t webapp:${BUILD_NUMBER} ."
            }
        }
        
        stage('Running Docker Image') {
            steps {
               sh "docker run --rm -p 3000:3000 -d --name webapp_ctr webapp:${BUILD_NUMBER} "
            }
        }
    }
    
}
