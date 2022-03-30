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
    stage("Parallel") {
      steps {
        parallel(
          "Taskone": {
            sh 'echo "First parallel stuff"'
          },
          "Tasktwo": {
            sh 'echo "Second parallel stuff"'
          }
        )
      }
    }
    stage('Test') {
      steps {
        sh 'echo "This is my Test step"'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "This is my Deploy step"'
        sh './dev-deploy.sh'
      }
    }
  }
}
