pipeline {
  agent any
  tools {
    maven 'maven3'
    jdk 'jdk8'
  }
  stages {
    stage('build') {
      steps {
      bat 'echo "PATH = ${PATH}"'
      bat 'echo "M2_HOME = ${M2_HOME}"'
      bat 'mvn -Dmaven.test.failure.ignore=true install' 
      }
    }
  }
}