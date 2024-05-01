pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'MAVEN, a build automation tool, is being used to compile and package the code.' 
            } 
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Using RSpec and TestNG to execute integration and unit tests.'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Integrating code analysis using Checkstyle.'
            }
        }
        
        stage('Security Scan') {
            steps {
                echo 'Performing security scan using Nmap'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'launching the programme on an AWS EC2 machine as a staging server.'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Executing integration tests to verify functionality in the staging environment.'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Launching an AWS EC2 instance as a production server for the application.'
            }
        }
    }

    post {
        always {
            emailext (
            subject: "Build Successful: ${env.JOB_NAME} [${env.BUILD_NUMBER}]",
            body: "The build succeeded.",
            to: "geetanjali.h02@gmail.com",
            attachLog: true
        )
        }
    }
}
