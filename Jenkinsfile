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
        sh 'echo "Hey there from GitHub 1"'
        sh "echo 'Hey there from GitHub 2'"
        echo "Hey there from GitHub 3"
        sh 'echo "This is my first step"'
      }
    }
    stage('Test') {
      when {
        branch 'feature-002' 
        anyOf {
          environment name: 'DEPLOY_TO', value: 'test'
          environment name: 'DEPLOY_TO', value: 'develop'
          environment name: 'DEPLOY_TO', value: 'prod'
        }
      }
      steps {
        sh 'echo "This is the Test step from feature-002"'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "This is my Deploy step"'
      }
    }
  }
}
