pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Build1') {
      steps {
        sh 'printenv|grep GIT'
      }
    }
    stage('Build2') {
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
