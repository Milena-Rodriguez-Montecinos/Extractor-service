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
        sh '''echo "docker build -t extractor_service:"${TAG_VERSION}" ."
'''
      }
    }

  }
  environment {
    TAG_VERSION = '1.0'
    DOCKER_HUB_PASSWORD = 'credentials(\'pass-Dockerhub\')'
    DOCKER_HUB_USER = 'mlnrdrgz-dockerhub'
  }
}