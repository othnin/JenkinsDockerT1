pipeline {
  agent {
    docker {image 'continuumio/miniconda3' }
  }
  stages {
    stage('Test') {
      steps {
        conda -V
      }
    }
  }
}

