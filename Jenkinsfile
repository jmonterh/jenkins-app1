pipeline {
  agent {
    any {
      image 'maven:3.3.3'
    }

  }
  stages {
    stage('build') {
      steps {
        sh '''mvn --version
pwd
echo "hello world in stage build"'''
        echo 'Segunda etpa'
      }
    }
    stage('Test stage2') {
      steps {
        echo 'Hello Stage 2'
      }
    }
  }
}