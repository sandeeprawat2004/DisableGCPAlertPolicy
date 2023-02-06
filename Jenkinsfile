pipeline {
    agent any
	environment{
		CLOUDSDK_CORE_PROJECT='premium-state-368208'
		CLIENT_EMAIL='581593856643-compute@developer.gserviceaccount.com'
		GCLOUD_CREDS=credentials('gcloud-creds')
	}

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
		sh '''
		gcloud auth activate-service-account  --key-file="$GCLOUD_CREDS"
		'''
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
