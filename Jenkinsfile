pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Get dependencies') {
      steps {
        sh '''apt-get install python-pip



'''
        sh 'pip install molecule'
      }
    }
    stage('test docker scenario') {
      steps {
        sh 'molecule test -s default'
      }
    }
    stage('Update Galaxy') {
      steps {
        sh 'ansible-galaxy login'
      }
    }
  }
}