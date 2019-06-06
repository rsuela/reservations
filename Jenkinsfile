pipeline {
  agent any
  tools {
    maven 'maven3'
    jdk 'jdk8'
  }
  stages {
    stage('build') {
      steps {
      batch 'echo "PATH = ${PATH}"'
      batch 'echo "M2_HOME = ${M2_HOME}"'
      batch 'mvn -Dmaven.test.failure.ignore=true install' 
      }
    }
  }
}