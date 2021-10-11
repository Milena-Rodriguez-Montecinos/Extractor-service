pipeline {
  agent any
  stages {
    stage('ExtractorService') {
      steps {
        sh 'echo "npm install"'
      }
    }

    stage('test-ExtractorService') {
      steps {
        sh 'echo "npm test"'
      }
    }

  }
}