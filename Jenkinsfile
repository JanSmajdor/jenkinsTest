def SERVICE
pipeline {
    agent any

    options {
        timeout(time: 3, unit: 'MINUTES')
        disableConcurrentBuilds(abortPrevious: true)
    }

    stages {
        stage('Print Environment Variables') {
            steps {
                echo 'Printing Environment Variables...'
                sh 'printenv'
            }
        }

        stage('Environment Setup from Webhook Payload') {
            steps {
                script {
                    def filepath = env.WEBHOOK_FILEPATH
                    echo "Parsed Payload: ${filepath}"

                    SERVICE = filepath.split('/')[0]
                    echo "Service: ${SERVICE}"
                }
            }
        }

        stage('Testing Global Variable Value') {
            steps {
                echo "Service: ${SERVICE}"
                echo "Waves Branch: ${env.GIT_BRANCH}"
            }
        }
    }
}