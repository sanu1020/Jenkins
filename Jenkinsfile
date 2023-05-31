pipeline {
    agent any
    tools{
        terraform 'Terraform'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM',gitcredentialId: [['GITHUB_ACCESS']], branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/sanu1020/eks-demo-jenkins']]])
            }
        }

        stage ('terraform destroy') {
            steps {
                sh ('terraform destroy --auto-approve')
            }
        }
    }
}