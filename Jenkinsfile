pipeline {
    agent {
        docker { image 'continuumio/miniconda3' args '-u root --privileged' }
    }
    stages {
        stage('Install') {
            steps {
                sh '''
                #whoami
                #chown 1000:1000 /.conda/envs/.conda_envs_dir_test
                #unset SUDO_UID SUDO_GID SUDO_USER
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


