pipeline {
  agent any

  stages {
    stage('Clone Repo') {
      steps {
        git 'https://github.com/rohanpatil18-eng/simple-ui.git'
      }
    }

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
