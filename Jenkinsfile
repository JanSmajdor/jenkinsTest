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
                echo "CHANGE_ID : ${env.CHANGE_ID}"
                echo "CHANGE_URL : ${env.CHANGE_URL}"
                echo "CHANGE_TITLE : ${env.CHANGE_TITLE}"
                echo "CHANGE_AUTHOR : ${env.CHANGE_AUTHOR}"
                echo "CHANGE_AUTHOR_DISPLAY_NAME : ${env.CHANGE_AUTHOR_DISPLAY_NAME}"
                echo "CHANGE_AUTHOR_EMAIL : ${env.CHANGE_AUTHOR_EMAIL}"
                echo "CHANGE_TARGET : ${env.CHANGE_TARGET}"
                echo "PR_ID/BRANCH_NAME : ${env.BRANCH_NAME}"
            }
        }
    }
}
