pipeline {
  agent {
    node { label 'nodejs' }
  }
  stages {
    stage ('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/dmstjd060/do400-pipelines-control.git'
      }
    }
    stages ('Run Tests') {
      parallel {
        stage ('Backend Tests') {
          steps {
            sh 'node ./backend/test.js'
          }
        }
        stage ('Frontend Tests') {
          steps {
            sh 'node ./frontend/test.js'
          }
        }
      }
    }
  }
}
