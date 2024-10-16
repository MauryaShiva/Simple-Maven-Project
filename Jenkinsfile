pipeline {
    agent any

    environment {
        MAVEN_HOME = tool 'Maven 3.9.9' // Adjust this according to your Maven installation in Jenkins
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
                // Run Maven build
                sh "'${MAVEN_HOME}/bin/mvn' clean install"
            }
        }

        stage('Test') {
            steps {
                // Run Maven tests
                sh "'${MAVEN_HOME}/bin/mvn' test"
            }
        }
        
        stage('Deploy') {
            steps {
                // Add deployment steps here
                echo 'Deploying application...'
                // e.g., sh "'${MAVEN_HOME}/bin/mvn' deploy"
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
