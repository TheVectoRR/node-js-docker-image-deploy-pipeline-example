pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo "Info: Building Docker Image"
                    sh "docker build -t nodejs-demo:latest"
                    echo "Info: Docker Image built"
                }
            }

        }
        
        stage('Deploy') {
            steps {
                script {
                    echo "Info: Running new Docker Image"
                    sh "docker rm -f nodejs-demo || true"
                    sh "docker run --restart always -p 3000:3000 -d --name nodejs-demo nodejs-demo:latest"
                    echo "Info: Deployed"
                }
            }

        }
    }
}
