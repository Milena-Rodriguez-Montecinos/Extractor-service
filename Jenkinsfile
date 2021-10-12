pipeline {
  agent any
  stages {
    stage('extractor_service') {
      steps {
        sh 'echo "npm install"'
      }
    }

    stage('Test') {
      post {
        success {
          publishHTML(allowMissing: false, alwaysLinkToLastBuild: false, keepAll: true, reportDir: 'Extractor-service/coverage/lcov-report/', reportFiles: 'index.html', reportName: 'Extractor service report')
        }
        always {
          archiveArtifacts 'Extractor-service/test-report.html'
        }

      }

      steps {
        dir(path: './Extractor-service') {
          sh 'npm test'
        }
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
        sh 'echo "Testing"'
       // sh 'echo "docker tag extractor_service:"${TAG_VERSION}" "${DOCKER_USER}"/extractor_service:"${TAG_VERSION}"'
       // sh 'echo "docker push "${DOCKER_USER}"/extractor_service:"${TAG_VERSION}"'
      }
    }

  }
  environment {
    TAG_VERSION = '1.0'
    DOCKER_USER = 'mlnrdrgz'
    DOCKER_PASSWORD = 'f6705dc3-bee3-46be-9945-33c23835142e'
  }
}