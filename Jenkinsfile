pipeline {
    agent any

    environment {
        KUBECONFIG = '/var/lib/jenkins/.kube/config'
    }

    stages {
        stage('Deploy to Kubernetes') {
            steps {
                // Debug: confirm kubectl sees the right cluster
                sh 'kubectl config view --minify'
                sh 'kubectl get nodes'

                // Apply manifests
                sh 'kubectl apply -f deploy.yaml --validate=false'
                sh 'kubectl apply -f service.yaml --validate=false'
            }
        }
    }
}
