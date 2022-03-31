pipeline {
  agent any  
  options {
    buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '15', daysToKeepStr: '', numToKeepStr: '5')
    disableConcurrentBuilds()
  }
  environment {
    DEPLOY_TO = 'prod'
  }
  stages {
    stage('Build') {
      steps {
        sh 'echo "Hey there from GitHub"'
      }
    }
    stage('Test') {
      steps {
        sh 'printenv'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "This is my Deploy step"'
      }
    }
  }
}
