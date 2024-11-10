pipeline {
    agent any

    tools {
        // Make sure to define ZAP as a tool in your pipeline
        zap 'ZAP'  // Replace 'ZAP' with the name you used in Global Tool Configuration
    }
    
    stages {
        stage('DAST - OWASP ZAP Scan') {
            steps {
                echo 'Running DAST with OWASP ZAP...'

                // Run OWASP ZAP security scan on the web application
                // Adjust the URL below to your local or deployed web app
                zapAttack(
                    url: 'http://172.27.210.185:8080/',  // Replace with your app URL
                    targetFile: '${env.WORKSPACE}/zap_report.html',  // Where to save the ZAP report
                    zapOptions: '-config api.disablekey=true'  // Disable API key for simplicity, adjust as needed
                )
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
