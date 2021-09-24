pipeline {
  agent {
    docker {image 'continuumio/miniconda3' }
  }
  stages {
    stage('Test') {
      steps {
        docker run -t -i continuumio/miniconda3 /bin/bash/conda
      }
    }
  }
}

