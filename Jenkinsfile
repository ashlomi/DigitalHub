pipeline {
    agent {
        label "master"
	}
    stages {
        stage("Export Porject") {
            steps {
             echo '**** mvn Build****'
			}
        }
        stage("Zip Project") {
            steps {
                echo '**** mvn Build****'    
            }
        }
        stage("Publish to Nexus") {
            steps {
			  echo "*** nexusVersion*****"       
			}
		}
	}		
    post { 
		always { 
			echo '----------Sending Build Notification to CDD--------------'
		}
		success { 
			sendNotificationToCDD appName: 'DigitalHub', 
					appVersion:  "${env.BRANCH_NAME}", 
					gitCommit: "${env.GIT_COMMIT}",
					gitPrevSuccessfulCommit: "${env.GIT_PREVIOUS_SUCCESSFUL_COMMIT}",
					overrideCDDConfig: [
							customApiKey: 'eyJhbGciOiJIUzUxMiJ9.eyJ1c2VybmFtZSI6ImFzaGxvbWl0ZXN0QGdtYWlsLmNvbSIsInRlbmFudElkIjoiZGQ5NTZiYjUtMWJlMC00ODU1LTg2MDYtYzUxNWM3OTI2ZTBjIiwidXNlcklkIjoxMSwianRpIjoiMjNiMjVjOGQtYWQ4NS00NmVmLTlhNmYtYjFjMzE1NDhjODg0IiwiZXhwIjoxNTgyNTI2MTgxfQ.4pHS5tIkQwqVzdrBPputzdJ4vZmWxbHKbvYnjgxRAfDdERKfuNEIrPEzXwn6Ew_0S9INci69Ub1LbeibfUJ3vw',
							customProxyPassword: '',
                            				customProxyUrl: '',
                           				customProxyUsername: '',
                            				customServerName: 'cddirector.io',
                            				customServerPort: 443,
                            				customTenantId: 'dd956bb5-1be0-4855-8606-c515c7926e0c',
                            				customUseSSL: true
                    			],
					releaseTokens: '{}'
		}
	}
}
