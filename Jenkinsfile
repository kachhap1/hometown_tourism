pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your Git repository
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/kachhap1/hometown_tourism.git']]])
            }
        }

        stage('Copy Files') {
            steps {
                // Use the bat step to run xcopy
                bat(script: 'xcopy /s /e /y "C:\\Users\\vicky\\OneDrive\\Desktop\\hometown_tourism" "C:\\Apache24"')
            }
        }

        // Add more stages as needed for your pipeline
    }

    post {
        success {
            // Define steps to execute on success
            echo 'The build was successful!'
        }
        failure {
            // Define steps to execute on failure
            echo 'The build failed!'
        }
    }
}
