pipeline {
    agent any

    stages {
        stage('Checkout Git Repositories') {
            steps {
                // Checkout first Git repository
                git(
                    url: 'https://github.com/CyrineAou/devops_frontend.git',
                    branch: 'main'
                )

                // Checkout second Git repository
                git(
                    url: 'https://github.com/CyrineAou/devops_backend.git',
                    branch: 'main'
                )


            }
        }

        stage('Build') {
            steps {
                // Perform build steps here
            }
        }

        // Add more stages as needed
    }
}