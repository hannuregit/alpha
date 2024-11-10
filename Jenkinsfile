pipeline {
    agent any
    stages {
        stage('Check Path') {
            steps {
                sh 'which dependency-check'  // Linux
                bat 'where dependency-check'  // Windows
            }
        }
    }
}
