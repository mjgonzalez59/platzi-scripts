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
<<<<<<< HEAD
      options {
          lock label: 'testing-deploy-envs', quantity: 1, variable: 'deployEnvarioment'
      }
      steps {
        sh 'echo "This is my Test Test Test step"'
=======
<<<<<<< HEAD
      steps {
        sh 'echo "This is my Test step"'
        echo "Deploying to to to to ${deployEnv}"
=======
      options {
          lock label: 'testing-deploy-envs', quantity: 1, variable: 'deployEnvarioment'
      }
      steps {
        sh 'echo "This is my Test step"'
>>>>>>> c9d00f8597f93147275673c47dd876e00dc63d46
>>>>>>> b34f0fc6de7f4937fe612ac98c36596985a87f18
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "This is my Deploy step"'
      }
    }
  }
}
