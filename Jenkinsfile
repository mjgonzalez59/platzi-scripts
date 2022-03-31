pipeline {
  agent any  
  enviroment {
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
