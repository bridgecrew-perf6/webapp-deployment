pipeline {
    agent any
tools {
    maven 'Maven3.0.5'
}

    stages {
        stage('Build') {
            steps {
                git branch: 'master', credentialsId: 'd5d06d3f-c518-44a7-88d4-e1a43039f283', url: 'https://github.com/guptarame/webapp-deployment.git'
                  }
                        }
         stage('Test') {
            steps {
                     sh 'mvn test'
                   }
                        }
        stage('package') {
            steps {
                       sh 'mvn package'
                   }
                         }
        stage('Results') {
             steps {
               junit '**/*.xml'
                archiveArtifacts artifacts: '**/*.war', followSymlinks: false
                  }
                         }
    stage('Deploy') {
             steps {
               deploy adapters: [tomcat9(credentialsId: 'd5d06d3f-c518-44a7-88d4-e1a43039f283', path: '', url: 'http://35.175.248.62:8090/')], contextPath: null, war: '**/*.war'
                    }
                  }
       }
}
