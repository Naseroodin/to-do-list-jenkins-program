pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building To-Do Application'
            }
        }

        stage('Test') {
            steps {
                sh 'test -f index.html'
                echo 'Test Passed'
            }
        }

        stage('Deploy') {
            steps {
                sh 'sudo cp index.html /var/www/html/'
                echo 'Application Deployed'
            }
        }

        stage('Verify') {
            steps {
                sh 'ls -l /var/www/html/'
                echo 'Deployment Verified'
            }
        }
    }

    post {
        success {
            echo 'Pipeline Completed Successfully'
        }

        failure {
            echo 'Pipeline Failed'
        }
    }
}
