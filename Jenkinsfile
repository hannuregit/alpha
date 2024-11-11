pipeline {
    agent any

    
    stages {
        stage('Snyk Security Scan') {
            steps {
                snykSecurity(
                    
                    severity: 'high',                 // Set severity threshold for issues (e.g., 'low', 'medium', 'high')
                    failOnIssues: true,               // Fail build if issues are found
                    monitorProjectOnBuild: true       // Monitor the project on Snyk (adds it to Snyk dashboard)
                )
            }
        }
    }
}
