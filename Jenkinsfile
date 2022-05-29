pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        echo 'echo "Build1"'
        git(url: 'https://github.com/guptarame/webapp-deployment.git', branch: 'blueocean', credentialsId: '34dcf6f4-7d4e-4a93-8edf-b31651b7586b', poll: true, changelog: true)
        withMaven(maven: 'Maven3.0.5', jdk: 'jdk1.8.0_312')
        tool(name: 'maven', type: 'Maven3.0.5')
      }
    }

    stage('Test') {
      steps {
        sh 'sh \'mvn test\''
      }
    }

    stage('package') {
      steps {
        sh 'sh \'mvn package\''
      }
    }

  }
}