pipeline {
  agent any
  tools {
    maven 'maven3'
    jdk 'jdk8'
  }
  stages {
    stage('build') {
      steps {
      bat 'set'
      bat 'mvn -Dmaven.test.failure.ignore=true install' 
      }
    }
  }
}