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
        kubectl create deployment nginx-1 --image=192.168.0.52:5000/multi-img:latest
        kubectl expose deployment nginx-1 --type=LoadBalancer --port=8080 \
                                               --target-port=80 --name=nginx-svc
        '''
      }
    }
  }
}
