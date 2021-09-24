pipeline {
    agent {
        docker { image 'continuumio/miniconda3' }
    }
    stages {
        stage('Install') {
            steps {
                sh 'conda --version'
            }
        }
    }
}


