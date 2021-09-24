pipeline {
    agent {
        docker { 
            image 'continuumio/miniconda3' 
            args '-u root --privileged'
        }
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
                #conda init bash
                '''
            }
        }
        stage('Run') {
            steps {
                sh '''#!/usr/bin/env bash
                source /opt/conda/etc/profile.d/conda.sh
                #conda run -n JDT1 /bin/bash -c
                conda activate /opt/conda/envs/JDT1
                python test.py
                '''
            }
        }
    }
}


