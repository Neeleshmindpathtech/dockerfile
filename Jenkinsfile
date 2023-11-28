pipeline {
  agent any
  stages {
    stage('Docker Build') {
    	agent any
      steps {
      	sh 'docker build -t neelesh/docker:latest .'
      }
    }
    stage('Scan') {
    	agent any
      steps {
      	sh 'trivy image neelesh/docker'
      }
    }
  }
}
