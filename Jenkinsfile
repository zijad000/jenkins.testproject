@Library('shared_library') _

pipeline {
  agent any
  environment {
	GIT_REPO_NAME="${srcRepoName}"   
	PROJECT_NAME = "${env.GIT_REPO_NAME == "" ? env.JOB_NAME.tokenize('/')[0] : env.GIT_REPO_NAME}"	

  }
  stages {
    stage('test') {
      steps {
        script {
			//echo env.getDisplayName()
			echo sh(returnStdout: true, script: 'env')
			echo '-----------------------------'
			echo scm.branches[0].name
			echo scm.userRemoteConfigs[0].credentialsId
			echo scm.userRemoteConfigs[0].url
			echo scm.userRemoteConfigs[0].name
			echo scm.userRemoteConfigs[0].refspec
			echo "${PROJECT_NAME}"
//			echo env.JOB_NAME.tokenize('/')[0]
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