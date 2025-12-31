pipeline {
  agent any
  stages {
    stage('git scm update') {
      steps {
        git url: 'https://github.com/simolin7812/nginx.git', branch: 'main'
      }
    }
    stage('deploy kubernetes') {
      steps {
        sh '''
        kubectl version
        '''
      }
    }
  }
}
