pipeline {
    agent any

     environment {
        SNYK_TOKEN = 'app.snyk.io/org/hannuregit'  // Provide your Snyk token here
    }

    
    stages {
        stage('Snyk Security Scan') {
            steps {
                snykSecurity(
                    snykInstallation: 'Snyk@latest',
                    severity: 'high',                 // Set severity threshold for issues (e.g., 'low', 'medium', 'high')
                    failOnIssues: true,               // Fail build if issues are found
                    monitorProjectOnBuild: true       // Monitor the project on Snyk (adds it to Snyk dashboard)
                )
            }
        }
    }
}
