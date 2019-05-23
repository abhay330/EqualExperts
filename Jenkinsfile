pipeline {
	environment {
		GIT_REPOSITORY = "${GITLAB_URL}/SpeedPayNextGen/NotificationRoutingService.git"
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
