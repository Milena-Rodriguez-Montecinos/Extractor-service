pipeline {
  agent any
  stages {
    stage('extractor_service') {
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
        sh 'echo "docker login -u "${DOCKER_USER}" -p "${DOCKER_PASSWORD}""'
      }
    }

    stage('publish') {
      steps {
        sh 'docker tag extractor_service:"${TAG_VERSION}" "${DOCKER_USER}"/extractor_service:"${TAG_VERSION}"'
        sh 'docker push "${DOCKER_USER}"/extractor_service:"${TAG_VERSION}"'
      }
    }

  }
  environment {
    TAG_VERSION = '1.0'
    DOCKER_USER = 'mlnrdrgz'
    DOCKER_PASSWORD = 'f6705dc3-bee3-46be-9945-33c23835142e'
  }
}