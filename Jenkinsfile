pipeline {
  agent any

  stages {

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t consent-ui .'
      }
    }

    stage('Run Container') {
      steps {
        sh '''
          docker rm -f consent-ui-container || true
          docker run -d -p 8081:80 --name consent-ui-container consent-ui
        '''
      }
    }

  }
}
