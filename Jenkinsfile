pipeline {
    agent any

    stages {
	stage('Test') {
            steps {
		sh '''
                gcloud version
		'''
            }
        }
        stage('Gcloud Auth') {
            steps {
		    withCredentials([file(credentialsId: 'gcloud-creds', variable: 'GCLOUD_CREDS')]) {
			sh '''
			gcloud auth activate-service-account '581593856643-compute@developer.gserviceaccount.com' --key-file='$GCLOUD_CREDS' --project='premium-state-368208'
			'''
		    }
            }
        }
	stage('Gcloud Disable Alert') {
            steps {
		sh '''
                gcloud alpha monitoring policies update projects/premium-state-368208/alertPolicies/3449565678435504101 --no-enabled
		'''
            }
        }
    }
}
