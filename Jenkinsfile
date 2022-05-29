pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'echo "Build1"'
      }
    }

    stage('Test') {
      steps {
        echo 'echo :Test1"'
      }
    }

    stage('package') {
      steps {
        echo 'package1'
      }
    }

    stage('deploy') {
      steps {
        echo 'deploy1'
      }
    }

  }
}