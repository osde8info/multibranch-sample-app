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
        withCredentials([gitUsernamePassword(credentialsId: 'github', gitToolName: 'Default')]) {
          sh 'printenv|grep GIT'
        }
      }
    }
    stage('Switch') {
      steps {
        sh 'git branch -a'
      }
    }
  }
  post {
    always {
      sh 'printenv|grep GIT'
    }
  }
}
