pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/guptarame/webapp-deployment.git', branch: 'blueocean', credentialsId: '34dcf6f4-7d4e-4a93-8edf-b31651b7586b')
      }
    }

    stage('test') {
      parallel {
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

    stage('Results') {
      steps {
        junit '**/*.xml'
        archiveArtifacts '**/*.war'
      }
    }

  }
}