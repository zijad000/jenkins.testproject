@Library('shared_library') _

pipeline {
  agent any
  environment {
	GIT_REPO_NAME="${srcRepoName}"    
  }
  stages {
    stage('test') {
      steps {
        script {
			//echo env.getDisplayName()
			echo sh(returnStdout: true, script: 'env')
			echo '-----------------------------'
			echo scm.branches[0].name
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