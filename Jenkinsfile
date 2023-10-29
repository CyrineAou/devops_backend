pipeline {
    agent any

    stages {
        stage('Checkout and Build Backend') {
            steps {
                // Checkout the backend repository
                checkout([$class: 'GitSCM', branches: [[name: 'main']], userRemoteConfigs: [[url: 'URL_TO_BACKEND_REPO']]])

                // Build the backend project
                sh 'mvn clean install' // Or your build command
            }
        }

        stage('Checkout and Build Frontend') {
            steps {
                // Clean the workspace to avoid conflicts
                deleteDir()

                // Checkout the frontend repository
                checkout([$class: 'GitSCM', branches: [[name: 'main']], userRemoteConfigs: [[url: 'URL_TO_FRONTEND_REPO']])

                // Build the frontend project
                sh 'npm install' // Install frontend dependencies
                sh 'ng build --prod' // Build the frontend (Angular in this example)
            }
        }

        stage('Deploy') {
            steps {
                // Your deployment steps for both backend and frontend
            }
        }
    }

    post {
        always {
            // Post-build actions
        }
    }
}