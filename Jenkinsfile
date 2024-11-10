pipeline {
    agent any

    stages {
        stage('DAST - OWASP ZAP Scan') {
            steps {
                echo 'Running DAST with OWASP ZAP Docker container...'

                // Run OWASP ZAP using Docker
                sh '''
                docker run -d --name zap -p 8080:8080 owasp/zap2docker-stable
                docker exec zap zap-cli start --daemon
                docker exec zap zap-cli active-scan http://172.27.210.185:8080/  # Replace with your app URL
                docker exec zap zap-cli report -o ${WORKSPACE}/zap_report.html
                docker stop zap
                '''
            }
        }

        stage('Clean Up') {
            steps {
                echo 'Cleaning up...'
                // Add any clean-up steps if necessary
            }
        }
    }
}
