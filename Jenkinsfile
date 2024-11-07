pipeline {
    agent any

    environment {
        // Set the location for your OWASP Dependency-Check HTML report
        DEPENDENCY_CHECK_HTML_REPORT = 'target/dependency-check-report/index.html'
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
                // Archive the Dependency-Check HTML report as a build artifact
                archiveArtifacts artifacts: 'target/dependency-check-report/index.html', allowEmptyArchive: true

                // Publish the HTML report to Jenkins
                publishHTML(target: [
                    reportName: 'OWASP Dependency-Check Report',
                    reportDir: 'target/dependency-check-report',
                    reportFiles: 'index.html',
                    alwaysLinkToLastBuild: false
                ])
            }
        }
    }
}
