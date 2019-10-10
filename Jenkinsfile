pipeline {
    agent {
        label 'java-jnlp'
    }
  stages {
    stage('checkout') {
      steps {
        container('maven'){
          git 'https://github.com/rsuela/reservations'
        }
      }
    }
    stage('build') {
      steps {
        container('maven'){
          sh "mvn -Dmaven.test.failure.ignore clean package"
        }
      }
    }
    stage('test') {
      steps {
        container('maven'){
          junit '**/target/surefire-reports/TEST-*.xml'
        }
      }
    }
    stage('archive') {
      steps {
        container('maven'){
          archive 'target/*.jar'
        }
      }
    }
  }
}
