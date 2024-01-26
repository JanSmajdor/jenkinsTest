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
        stage('Environment Variable Test') {
            steps {
                echo "GIT BRANCH : ${env.GIT_BRANCH}"
            }
        }
    }
}
