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
                    def changes = currentBuild.changeSets
                    for (changeSet in changes) {
                        for (entry in changeSet) {
                            def filePath = entry.path
                            echo "Changed file: $filePath"
                        }
                }
            }
        }
    }
}
