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
        sh 'docker run -d -p 8080:8080 -v ${PWD}/webapps:/usr/local/tomcat/webapps my-tomcat-image'
      }
    }
  }
}

