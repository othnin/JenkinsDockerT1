pipeline {
    agent {
        docker { image 'continuumio/miniconda3' }
    }
    stages {
        stage('Install') {
            steps {
                sh 'conda --version'
                sh 'conda env create -f environment.yaml'
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


