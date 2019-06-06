pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        git(url: 'https://github.com/rsuela/reservations.git', branch: 'master', poll: true)
      }
    }
  }
}