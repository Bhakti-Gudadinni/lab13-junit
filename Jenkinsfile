pipeline {
    agent any

    tools {
        jdk 'JDK17'
        maven 'Maven3'
    }

    stages {
        // REMOVED the 'Checkout' stage because Jenkins does this automatically
        
        stage('Build & Test') {
            steps {
                // Use 'bat' for Windows-based Jenkins (based on your logs)
                bat 'mvn clean test'
            }
            post {
                always {
                    junit '**/target/surefire-reports/*.xml'
                }
            }
        }
    }
}
