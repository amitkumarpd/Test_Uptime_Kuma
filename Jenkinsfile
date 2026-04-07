pipeline {
    agent any

    environment {
        KUBECONFIG = '/home/jenkins/.kube/config'
    }

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'git@github.com:amitkumarpd/Test_Uptime_Kuma.git'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh '/usr/local/bin/kubectl apply -f deploy.yaml --validate=false'
                sh '/usr/local/bin/kubectl apply -f service.yaml --validate=false'
            }
        }
    }
}
