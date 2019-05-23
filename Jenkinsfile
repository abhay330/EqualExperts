pipeline {
	environment {
		GIT_REPOSITORY = "https://github.com/abhay330/EqualExperts.git"
	}

	agent {
		node {
			label "Windows"
			customWorkspace "workspace/${JOB_NAME}"
		}
	}
	
	stages {
		stage ("Initialization") {
			steps {
				cleanWs()
				git poll: true , branch: env.BRANCH_NAME, credentialsId: env.GIT_CREDENTIALS, url: env.GIT_REPOSITORY
				initVersion(prefix: env.VERSION_PREFIX)
			}
		}		
	}

	post {
	}
}
