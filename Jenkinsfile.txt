pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                bat 'python app/main.py'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                bat 'pytest tests'
            }
        }
        stage('Deploy to Staging') {
            when {
                branch 'develop'
            }
            steps {
                echo 'Deploying to staging...'
                bat 'echo Simulated staging deploy'
            }
        }
        stage('Deploy to Production') {
            when {
                branch 'main'
            }
            steps {
                echo 'Deploying to production...'
                bat 'echo Simulated production deploy'
            }
        }
    }
}
