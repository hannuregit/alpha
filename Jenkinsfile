pipeline {
    agent any

    environment {
        SNYK_TOKEN = 'app.snyk.io/org/hannuregit' 
        PROJECT_PATH = '/var/lib/jenkins/workspace/Alpha'  // Set project directory path
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://your-repository-url.git'
            }
        }

        stage('Snyk Scan') {
            steps {
                script {
                    // Use environment variable to specify directory
                    dir("${env.PROJECT_PATH}") {
                        snykSecurity(
                            snykInstallation: 'Snyk',
                            failOnIssues: true,
                            monitor: true,
                            test: true
                        )
                    }
                }
            }
        }
    }
}
