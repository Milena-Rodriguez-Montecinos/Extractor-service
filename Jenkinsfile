pipeline {
  agent any
  stages {
    stage('ExtractorService') {
      steps {
        sh 'echo "npm install"'
      }
    }

    stage('test') {
      steps {
        sh 'echo "npm test"'
      }
    }

    stage('package') {
      steps {
        sh 'echo "docker build -t extractor_service:"${TAG_VERSION}" ." '
      }
    }

    stage('authentication') {
      steps {
        sh 'echo "Hello fucking world"'
      }
    }

  }
  environment {
    TAG_VERSION = '1.0'
  }
}