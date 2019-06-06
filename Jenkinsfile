pipeline {
  agent any
  tools {
    maven 'maven3'
    jdk 'jdk8'
  }
  stages {
    stage('build') {
      steps {
      sh '''
          echo "PATH = ${PATH}"
          echo "M2_HOME = ${M2_HOME}"
         '''
      sh 'mvn -Dmaven.test.failure.ignore=true install' 
      }
    }
  }
}