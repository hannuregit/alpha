pipeline {
    agent any

    environment {
        PROJECT_PATH = '/var/lib/jenkins/workspace/Alpha'  // Set project directory path
    }

    stages {
        stage('Snyk Scan') {
            steps {
                script {
                    // Use environment variable to specify directory
                    dir("${env.PROJECT_PATH}") {
                        snykSecurity(
                            snykInstallation: 'Snyk',  // Ensure Snyk is configured in Global Tool Config
                            failOnIssues: true
                        )
                    }
                }
            }
        }
    }
}
