pipeline {
    agent any

    environment {
        MAVEN_HOME = tool 'Maven 3.9.9' // Adjust this to match your Maven installation
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from SCM (Git)
                git branch: 'main', url: 'https://github.com/MauryaShiva/Simple-Maven-Project.git'
            }
        }

        stage('Build') {
            steps {
                // Run Maven build on Windows
                bat "${MAVEN_HOME}\\bin\\mvn clean install"
            }
        }

        stage('Test') {
            steps {
                // Run Maven tests on Windows
                bat "${MAVEN_HOME}\\bin\\mvn test"
            }
        }
        
        stage('Deploy') {
            steps {
                // Add deployment steps here
                echo 'Deploying application...'
                // e.g., bat "${MAVEN_HOME}\\bin\\mvn deploy"
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
