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
			echo params.RepoRef
			echo params.RepoCredentials
			echo scm.userremoteconfigs.credentialsid
			echo params
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