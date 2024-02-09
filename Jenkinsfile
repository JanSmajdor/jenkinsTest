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
                        echo "Filepath: ${filepath}"
                    
                        SERVICE = filepath.split('/')[0]
                        echo "Service: ${SERVICE}"

                    } catch (Exception err) {
                        println("Global Setup Stage Exception Message: ${err}")
                    }
                }
            }
        }

        stage('Trigger AnsibleTower') {
            try {
                ansibleTower(
                    towerServer: 'AnsibleTower',
                    towerCredentialsId: 'AnsibleAutomationStagingDeploy',
                    templateType: 'job',
                    jobTemplate: 'Automation - Deploy to Staging account [Mono Repo]',
                    towerLogLevel: 'full',
                    inventory: '',
                    jobTags: '',
                    skipJobTags: '',
                    limit: '',
                    removeColor: false,
                    verbose: true,
                    credential: '',
                    extraVars: """---
                        SERVICE: '${SERVICE}'
                        WAVES_BRANCH: '${env.GITHUB_BRANCH}'
                        UPDATE_ENVS: 'true'
                    """,
                    async: false
                )
                deleteDir()
            } catch (Exception err) {
                println("Trigger AnsibleTower Stage Exception Message: ${err}")
            }
        }
    }
}