pipeline {
    agent any

    stages {
        stage('Gcloud Auth') {
            steps {
                gcloud auth activate-service-account 581593856643-compute@developer.gserviceaccount.com --key-file=key-file.json --project=premium-state-368208
            }
        }
		stage('Gcloud Disable Alert') {
            steps {
                gcloud alpha monitoring policies update projects/premium-state-368208/alertPolicies/3449565678435504101 --no-enabled
            }
        }
    }
}