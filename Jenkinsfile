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
                    if(env.payload) {
                        echo "Payload found in webhook request: "
                        echo "${env.payload}"
                    }
                    else{
                        echo "Payload could NOT be found in webhook request."
                    }
                }
            }
        }
    }
}
