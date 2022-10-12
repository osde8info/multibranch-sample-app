pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Build1') {
      agent {
        docker {
          image('python:3.7-slim-bullseye')
        }
      }
      steps {
        sh 'printenv|grep GIT'
        sh 'python --version'
      }
    }
    stage('Build2') {
      agent {
        docker {
          image('python:3.7-slim-bullseye')
        }
      }
      steps {
        withCredentials([gitUsernamePassword(credentialsId: 'github', gitToolName: 'Default')]) {
          sh 'printenv|grep GIT'
        sh 'python --version'
        }
      }
    }
    stage('Switch') {
      agent {
        docker {
          image('python:3.7-slim-bullseye')
        }
      }
      steps {
        sh 'python --version'
      }
    }
  }
  post {
    always {
      sh 'printenv|grep GIT'
    }
  }
}
