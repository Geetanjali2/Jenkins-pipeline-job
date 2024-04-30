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

    post {
        always {
            emailext(
                mimeType: 'text/html',
                to: 'geetanjali.h02@gmail.com',
                subject: "Jenkins Pipeline Status: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """
                    <html>
                        <body>
                            <h1>Pipeline Completion Report</h1>
                            <p><strong>Build:</strong> ${env.JOB_NAME} #${env.BUILD_NUMBER}</p>
                            <p><strong>Status:</strong> ${currentBuild.currentResult}</p>
                            <p><strong>Build URL:</strong> <a href="${env.BUILD_URL}">${env.BUILD_URL}</a></p>
                        </body>
                    </html>
                """,
                attachLog: true
            )
        }
        failure {
            emailext(
                mimeType: 'text/html',
                to: 'geetanjali.h02@gmail.com',
                subject: "FAILURE in Pipeline: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """
                    <html>
                        <body>
                            <h1>Pipeline Failure Report</h1>
                            <p><strong>Build:</strong> ${env.JOB_NAME} #${env.BUILD_NUMBER}</p>
                            <p><strong>Status:</strong> ${currentBuild.currentResult}</p>
                            <p><strong>Build URL:</strong> <a href="${env.BUILD_URL}">${env.BUILD_URL}</a></p>
                        </body>
                    </html>
                """,
                attachLog: true
            )
        }
    }
}
