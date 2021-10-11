pipeline {
  agent any
   environment {
    TAG_VERSION = '1.0'
  }
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh '''echo "Building" '''
          }
        }

        stage('ExtractorService') {
          steps {
            sh 'echo "npm install"'
          }
        }

      }
    }

  }
}