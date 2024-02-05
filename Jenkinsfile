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

        stage('Print Environment Variables available to this job') {
            steps {
                echo "env:  ${env.getEnvironment()}"
            }
        }

        stage('Environment Variable Test') {
            steps {
                echo "GIT BRANCH : ${env.GIT_BRANCH}"
            }
        }
    }
}
