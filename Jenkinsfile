pipeline {
  agent any
  stages {
    stage('Docker Build') {
    	agent any
      steps {
      	sh 'docker build -t neelesh1/docker .'
      }
    }
    stage('Scan') {
    	agent any
      steps {
      	sh 'trivy image neelesh1/docker'
      }
    }
  }
}
