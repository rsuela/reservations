pipeline {
  agent {
    kubernetes {
      label 'kubernetes'
      defaultContainer 'maven'
      yaml """
apiVersion: v1
kind: Pod
metadata:
  labels:
    label: kubernetes
spec:
  containers:
  - name: maven
    image: maven:3.5.2-jdk-8-alpine
    command:
    - cat
    tty: true
  - name: busybox
    image: busybox
    command:
    - cat
    tty: true
"""
    }
  }
  stages {
    stage('checkout') {
      steps {
        container('maven') {
          git https://github.com/rsuela/reservations
        }
      }
    }
  }
}
