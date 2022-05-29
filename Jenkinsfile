pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/guptarame/time-tracker.git', branch: 'blueocean')
      }
    }

    stage('test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('package') {
      steps {
        sh 'mvn package'
      }
    }

  }
}