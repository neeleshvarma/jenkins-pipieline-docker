pipeline {
  agent none
  stages {
    stage('Maven Install') {
      agent {
        docker {
          image 'maven:3.5.0'
        }
      }
      steps {
        sh 'mvn clean install'
      }
    }
    stage('Docker Build') {
      agent {
      	dockerfile true
      }
      steps {
        sh 'docker build -f Dockerfile -t docker-springboot.jar .'
      }
    }
  }
}
