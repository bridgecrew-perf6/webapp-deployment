pipeline {
    agent any
tools {
    maven 'MAVEN_HOME'
}


    stages {
        stage('Build') {
            steps {
                git credentialsId: '34dcf6f4-7d4e-4a93-8edf-b31651b7586b', url: 'https://github.com/guptarame/webapp-deployment.git'                  
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
