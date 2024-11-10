pipeline {
    agent any

    stages {
        stage('SCA') {
            steps {
                dependencyCheck additionalArguments: '--out ./dependency-check-reports', odcInstallation: 'OWASP-Dependency-Scan'
                dependencyCheckPublisher pattern: '**/dependency-check-reports/dependency-check-report.xml'
            }
        }
    }
}
