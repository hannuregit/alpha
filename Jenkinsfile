pipeline {
    agent any

    environment {
        // Set the location for your OWASP Dependency-Check HTML report
        DEPENDENCY_CHECK_HTML_REPORT = 'alpha/storefile'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                checkout scm
            }
        }

        stage('Run OWASP Dependency-Check') {
            steps {
                // Run OWASP Dependency-Check with HTML output
                sh '''
                    dependency-check --project "YourProject" --scan . --out target --format "HTML"
                '''
            }
        }

        stage('Archive and Publish HTML Report') {
            steps {
                

                // Publish the HTML report to Jenkins
                publishHTML(target: [
                    reportName: 'OWASP Dependency-Check Report',
                    reportDir: 'alpha/storefile',
                    reportFiles: 'index.html',
                    alwaysLinkToLastBuild: false
                ])
            }
        }
    }
}
