@Library('shared_library') _

pipeline {
  agent any
  environment {

  }
  stages {
    stage('test') {
      steps {
        script {
			echo env
        }
      }
    }
  }
  post {
    always {
       cleanWs()     
    }
  }
}