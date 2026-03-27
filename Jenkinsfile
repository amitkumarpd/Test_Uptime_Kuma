pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'git@github.com:amitkumarpd/Test_Uptime_Kuma.git'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'sudo -u amitkumar kubectl apply -f deploy.yaml'
                sh 'sudo -u amitkumar kubectl apply -f service.yaml'
            }
        }
    }
}
