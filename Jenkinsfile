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
    stage('SampleTryCatch') {
      steps {
        script{
          try {
            echo 'Code in the try block'
            sh 'exit 1'
          }
          catch (exc) {
            echo 'Something went wrong and work and got some exceptions'
            throw exc
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "This is my Deploy step"'
      }
    }
  }
}
