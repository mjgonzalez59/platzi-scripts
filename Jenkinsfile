pipeline {
  agent any
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
        branch 'production'
        anyOf {
          environment name: 'DEPLOY_TO', value: 'prod'
          environment name: 'DEPLOY_TO', value: 'test'
        }
      }
      steps {
        sh 'echo "This is my Test step"'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "This is my Deploy step"'
      }
    }
  }
}
