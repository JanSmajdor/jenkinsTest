pipeline {
    agent any

    environment {
        service = ''
    }

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

                    env.service = filepath.split('/')[0]
                    echo "Service: ${env.service}"
                }
            }
        }
    }
}