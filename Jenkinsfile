pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo "Hey there from GitHub 1"'
        sh "echo 'Hey there from GitHub 2'"
        echo 'Hey there from GitHub 3'
        sh 'echo "This is my first step"'
      }
    }
    stage('Test') {
      when {
        not { branch 'master' }
      }
      options {
          lock label: 'testing-deploy-envs', quantity: 1, variable: 'deployEnvarioment'
      }
      steps {
        sh 'echo "This is my Test Test Test step"'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "This is my Deploy step"'
      }
    }
  }
}
