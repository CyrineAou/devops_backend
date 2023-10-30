pipeline {
    agent any

    stages {
        stage('Checkout and Build Backend') {
            steps {
                // Checkout the backend repository
                checkout([$class: 'GitSCM', branches: [[name: 'main']], userRemoteConfigs: [[url: 'https://github.com/CyrineAou/devops_backend.git']]])

                // Build the backend project
                sh 'mvn clean install' // Or your build command
            }
        }

        stage('Checkout and Build Frontend') {
            steps {
                // Clean the workspace to avoid conflicts
                deleteDir()

                // Checkout the frontend repository
                checkout([$class: 'GitSCM', branches: [[name: 'main']], userRemoteConfigs: [[url: 'https://github.com/CyrineAou/devops_frontend.git']])

                // Build the frontend project
                sh 'npm install' // Install frontend dependencies
                sh 'ng build --prod' // Build the frontend (Angular in this example)
            }
        }
    }
}
