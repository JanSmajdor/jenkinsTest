pipeline {
    agent any

    options {
        timeout(time: 3, unit: 'MINUTES')
        disableConcurrentBuilds(abortPrevious: true)
    }

    stages {
        stage('Print Environment') {
            steps {
                echo 'Printing Environment Variables...'
                sh 'printenv'
            }
        }
    }
}
