pipeline {
  agent any
  
  stages {
    stage('Build Docker Image') {
      steps {
        script {
          docker.image('tomcat:latest').pull()
          docker.build('my-tomcat-image', '-f Dockerfile .')
        }
      }
    }
    
    stage('Deploy to Local Directory') {
      steps {
        sh 'docker run -d -p 8282:8282 -v ${PWD}/webapps:/home/user/Images my-tomcat-image'
      }
    }
  }
}

