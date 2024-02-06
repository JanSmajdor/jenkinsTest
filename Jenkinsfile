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
                    e// Access the variable
                    def githubPayload = env.WEBHOOK_FILEPATH

                    // Parse the JSON payload if it's in JSON format
                    def webhook_filepath = readJSON text: githubPayload

                    // Use the parsed data
                    echo "Parsed Payload: ${webhook_filepath}"
                }
            }
        }
    }
}