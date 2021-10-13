@Library('shared_library') _

pipeline {
  agent any
  environment {
	GIT_REPO_NAME="${srcRepoName}"   
	//PROJECT_NAME = "${env.GIT_REPO_NAME == "" ? env.JOB_NAME.tokenize('/')[0] : env.GIT_REPO_NAME}"	
	PROJECT_NAME=getEnvName("${srcRepoName}", env.JOB_NAME.tokenize('/')[0])

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
			echo env.PROJECT_NAME
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

def getEnvName(customValue, defaultValue) {
    def result
	if(customValue = null) {
        result = defaultValue;
    }  else {
        result = customValue;
    }
	echo '*********'
	echo result 
	return result
}