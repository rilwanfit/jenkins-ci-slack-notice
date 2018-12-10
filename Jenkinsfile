/* import shared library */
@Library('jenkins-shared-library')_

pipeline {
    agent { docker { image 'php' } }

    stages {
        stage('build') {
            steps {
                sh 'php --version'
            }
        }
    }
    post {
        always {
	    /* Use slackNotifier.groovy from shared library and provide current build result as parameter */
            slackNotifier(1)
            cleanWs()
        }
    }
}