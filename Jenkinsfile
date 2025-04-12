pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Deploy to Staging') {
            steps {
                bat 'deploy_staging.bat'
            }
        }

        stage('Deploy to Production') {
            steps {
                bat 'deploy_production.bat'
            }
        }
    }
}
