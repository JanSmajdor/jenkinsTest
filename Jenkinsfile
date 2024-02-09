def SERVICE
pipeline {
    agent any

    stages {
        stage('Print Environment Variables') {
            steps {
                echo 'Printing Environment Variables...'
                sh 'printenv'
            }
        }

        stage('Global Setup') {
            steps {
                script {
                    try {
                        def filepath = env.WEBHOOK_FILEPATH
                    
                        SERVICE = filepath.split('/')[0]
                        echo "Service: ${SERVICE}"

                    } catch (Exception err) {
                        println("Global Setup Stage Exception Message: ${err}")
                    }
                }
            }
        }
    }
}