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
      try {
        sh 'exit 1'
      }
      catch (exc) {
        echo "Something didn't work and got some exceptions"
        throw
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "This is my Deploy step"'
      }
    }
  }
}
