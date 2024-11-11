pipeline {
    agent any

    
    stages {
        stage('Snyk Security Scan') {
            steps {
                snykSecurity(
                    organization: 'your-org-name',   // Optional: specify your Snyk organization
                    projectName: 'your-project-name', // Optional: name the project in Snyk
                    severity: 'high',                 // Set severity threshold for issues (e.g., 'low', 'medium', 'high')
                    failOnIssues: true,               // Fail build if issues are found
                    monitorProjectOnBuild: true       // Monitor the project on Snyk (adds it to Snyk dashboard)
                )
            }
        }
    }
}
