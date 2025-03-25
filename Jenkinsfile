pipeline {
    agent any 
    tools {
        maven 'apache-maven-3.0.1' 
      // musi być taka sama nazwa jak w Jenkins -> Manage Jenkins -> Tools -> Maven instalation
    }
    stages {
        stage('build') { 
            steps {
              echo 'compiling sysfoo app'
              sh 'mvn compile'
            }
        }
        stage('test') { 
            steps {
              echo 'running unit tests'
              sh 'mvn clean test'
            }
        }
        stage('package') { 
            steps {
              echo 'packaging the app'
              sh 'mvn package -DskipTests'
            }
        }
    }
  post{
    always{
      echo 'This pipeline is competed..'
    }
  }
}
