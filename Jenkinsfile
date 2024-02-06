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
                    def payloadMap = readJSON text: payload
                    if(env.payloadMap) {
                        echo "Payload found in webhook request: "
                        echo "${env.payloadMap}"
                    }
                    else{
                        echo "Payload could NOT be found in webhook request."
                    }
                }
            }
        }
    }
}
