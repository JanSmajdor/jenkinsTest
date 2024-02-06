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

        stage('Webhook Payload') {
            steps {
                script {
                    def filepath = env.WEBHOOK_FILEPATH
                    // Use the parsed data
                    echo "Parsed Payload: ${filepath}"
                }
            }
        }
    }
}