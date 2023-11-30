pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                sh 'docker build -t ram6 .'
            }
        }
        
        stage('Trivyscan') {
            steps {
                sh "echo 'Neelesh@1234' | sudo -S trivy image --format template --template @/usr/local/share/trivy/templates/html.tpl -o ram6.html ram6"
                publishHTML target : [
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: '.',
                    reportFiles: 'ram6.html',
                    reportName: 'Trivy Scan',
                    reportTitles: 'Trivy Scan'
                ]
            }
        }
    }
}
