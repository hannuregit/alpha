pipeline {
    agent any

    stages {
        stage('Dependency Check') {
            steps {
                echo 'Running OWASP Dependency-Check...'

                // Run OWASP Dependency-Check using Docker
                sh '''
                sudo docker run --rm -v $(pwd):/src -v $(pwd)/odc-report:/report owasp/dependency-check \
                --scan /src --format HTML --out /report/dependency-check-report.html
                '''
            }
        }

        stage('Publish Dependency Check Report') {
            steps {
                publishHTML([
                    allowMissing: false,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: 'odc-report',
                    reportFiles: 'dependency-check-report.html',
                    reportName: 'OWASP Dependency Check Report'
                ])
            }
        }
    }
}
