
pipeline {
    agent any

    options {
        timestamps()
        disableConcurrentBuilds()
    }

    stages {
        stage('Checkout Verification') {
            steps {
                echo 'GitHub checkout completed successfully.'
                sh 'git --version'
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('Trivy Verification') {
            steps {
                sh 'trivy --version'
            }
        }

        stage('Docker Verification') {
            steps {
                sh 'docker --version'
            }
        }
    }

    post {
        success {
            echo 'DeployX test pipeline completed successfully.'
        }

        failure {
            echo 'Pipeline failed. Check the console output.'
        }
    }
}
