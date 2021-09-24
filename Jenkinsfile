pipeline {
    agent {
        docker { image 'continuumio/miniconda3' }
    }
    stages {
        stage('Install') {
            steps {
                sh '''
                unset SUDO_UID SUDO_GID SUDO_USER
                conda --version
                conda env create -f environment.yaml
                '''
            }
        }
        stage('Run') {
            steps {
                sh '''
                source activate JDT1
                python test.py
                '''
            }
        }
    }
}


