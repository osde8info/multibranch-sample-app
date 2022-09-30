pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Build1') {
      steps {
        sh 'printenv|grep GIT'
        sh 'printenv|grep GIT'
      }
    }
    stage('Build2') {
      steps {
        withCredentials([gitUsernamePassword(credentialsId: 'github', gitToolName: 'Default')]) {
          sh 'printenv|grep GIT'
          sh 'printenv|grep GIT'
        }
      }
    }
    stage('Switch') {
      steps {
        checkout([$class: 'GitSCM',
          branches: [[name: '01-warnings-ng']],
                  userRemoteConfigs: [[url: {GIT_URL}]]])
        sh 'git branch'
      }
    }
  }
  post {
    always {
      sh 'date'
    }
  }
}
