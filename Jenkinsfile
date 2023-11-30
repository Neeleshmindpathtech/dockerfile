pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                sh 'docker build -t ram-ram .'
            }
        }
        
        stage('T-scan') {
            steps {
                sh 'sudo trivy image --format template --template "@/usr/share/trivy/templates/html.tpl" -o report.html ram-ram'
            }
        }
    }
}
