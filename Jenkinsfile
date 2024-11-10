pipeline {
    agent any

  

    stages {
        stage('DAST - OWASP ZAP Scan') {
            steps {
                echo 'Running DAST with OWASP ZAP...'

                // Run OWASP ZAP security scan using the ZAP CLI
                // You can replace the ZAP URL and parameters accordingly
                sh '''
                zap-cli start --daemon  # Start ZAP in daemon mode
                zap-cli active-scan http://172.27.210.185:8080/  # Run active scan on your app URL
                zap-cli report -o ${WORKSPACE}/zap_report.html  # Save the report to the Jenkins workspace
                zap-cli stop  # Stop ZAP after scan
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
