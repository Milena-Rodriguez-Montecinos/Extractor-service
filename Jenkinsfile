pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh '''echo "npm install"
'''
          }
        }

        stage('ExtractorService') {
          steps {
            sh 'echo "npm install"'
          }
        }

      }
    }

    stage('test') {
      steps {
        sh 'echo "Testing"'
      }
    }

  }
}