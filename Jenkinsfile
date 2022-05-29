pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/guptarame/time-tracker.git', branch: 'master', credentialsId: 'cred')
      }
    }

  }
}