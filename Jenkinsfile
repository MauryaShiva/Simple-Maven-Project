pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from SCM (Git)
                git branch: 'main', url: 'https://github.com/MauryaShiva/Simple-Maven-Project.git'
            }
        }

        stage('Build') {
            steps {
                // Run Maven build
                bat 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Run Maven tests
                bat 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
