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

    stage('login to docker hub') {
      steps {
        sh '''sh \'echo $DOCKERHUB_CREDENTIALS_PSW | sudo docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin\'                		
	echo \'Login Completed\'      '''
      }
    }

    stage('Push image to docker hub') {
      steps {
        sh ''' sh \'sudo docker push 19880402/jenkins-master:$BUILD_NUMBER\'           
echo \'Push Image Completed\'   '''
      }
    }

  }
  environment {
    dockerhub = 'dckr_pat_b80H3VCqXRl_m_XQRebWHvGa9PM'
  }
}