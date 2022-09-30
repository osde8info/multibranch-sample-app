pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Build') {
      steps {
        sh 'printenv'
      }
    }
  }
  post {
    always {
      sh 'date'
    }
  }
}
