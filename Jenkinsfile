pipeline {
    agent {
        label 'java-jnlp'
    }
  stages {
    stage('checkout') {
      steps {
          git 'https://github.com/rsuela/reservations'
      }
    }
    stage('build') {
      steps {
          sh "mvn -Dmaven.test.failure.ignore clean package"
      }
    }
    stage('test') {
      steps {
          junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('archive') {
      steps {
          archive 'target/*.jar'
      }
    }
  }
  post {
      always{
          logstashSend failBuild: true, maxLines: 1000
      }
  }
}
