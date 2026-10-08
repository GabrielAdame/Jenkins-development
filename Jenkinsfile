pipeline {
    agent {
        label 'build-agent'
    }

    stages {
        stage('Build Environment') {
            steps {
                sh '''
                    hostname
                    pwd
                    dotnet --info
                '''
            }
        }

        stage('Deployment Environment') {
            agent {
                label 'deploy-agent'
            }
            steps {
                sh '''
                    hostname
                    pwd
                    git --version
                    kubectl version --client
                    curl --version
                '''
            }
        }
    }
}

