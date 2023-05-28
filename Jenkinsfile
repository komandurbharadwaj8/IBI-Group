ipeline {
    agent any

    stages {
        stage('Build and Push Docker image') {
            steps {
                script {
                    // Build the Docker image
                    docker.build('bharadwajaws/nginx-server:latest', '.')

                    // Push the Docker image to Docker Hub
                    docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                        docker.image('bharadwajaws/nginx-server:latest').push()
                    }
                }
            }
        }
    }
}
