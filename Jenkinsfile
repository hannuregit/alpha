pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Simple build steps, such as validating HTML or copying files to the build location
                echo 'Building the Hello World project...'
                
                // Example of validating the HTML file (if you have an HTML validator installed)
                sh 'html-validator index.html'  // Validates the HTML file (replace with your own validation if necessary)
                
                // Alternatively, you can add steps like minifying the HTML, copying files, or packaging if needed
            }
        }
        
        stage('Clean Up') {
            steps {
                echo 'Cleaning up...'
                // Add clean-up steps here if needed
            }
        }
    }
}
