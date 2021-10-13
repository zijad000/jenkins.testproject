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
			echo scm.userRemoteConfigs[1].credentialsId
//			echo "${git_credentials}".[0]
//			echo '${git_credentials}'.[0]
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