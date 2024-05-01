pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'MAVEN, a build automation tool, is being used to compile and package the code.' 
                }
            post {
                success {
                    echo 'Build successfully!'
                }
                failure {
                    echo 'Build failed!'
                }
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Using RSpec and TestNG to execute integration and unit tests.'
            }
            post {
                success {
                    echo 'Tests passed!'
                }
                failure {
                    echo 'Tests failed!'
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Integrating code analysis using Checkstyle.'
            }
            post {
                success {
                    echo 'Code analysis passed!'
                }
                failure {
                    echo 'Code analysis failed!'
                }
            }
        }
        
        stage('Security Scan') {
            steps {
                echo 'Performing security scan using Nmap'
            }
            post {
                success {
                    echo 'Security scan passed!'
                }
                failure {
                    echo 'Security scan failed!'
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'launching the programme on an AWS EC2 machine as a staging server.'
            }
             post {
                success {
                    echo 'Deployment to staging successful!'
                }
                failure {
                    echo 'Deployment to staging failed!'
                }
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Executing integration tests to verify functionality in the staging environment.'
            }
            post {
                success {
                    echo 'Integration tests on staging passed!'
                }
                failure {
                    echo 'Integration tests on staging failed!'
                }
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Launching an AWS EC2 instance as a production server for the application.'
            }
             post {
                success {
                    echo 'Deployment to production successful!'
                }
                failure {
                    echo 'Deployment to production failed!'
                }
            }
        }
    }

    post{
        always{
              mail to: "azadehghneiat@gmail.com",
              subject: "Build Status Email",
              body: "Build log attached!"
                }
        }
}
