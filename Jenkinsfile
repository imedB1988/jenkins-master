pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'npm   install'
      }
    }

    stage('test') {
      steps {
        sh 'npm test'
      }
    }

    stage('checkout') {
      steps {
        git(url: 'https://github.com/imedB1988/jenkins-master.git', branch: 'master')
      }
    }

  }
}