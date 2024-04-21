pipeline{
    environment {
        DIRECTORY_PATH = "${env.WORKSPACE}"  // Update path as needed
        TESTING_ENVIRONMENT = 'test'
        PRODUCTION_ENVIRONMENT = "${env.Geet}"
    }
    agent any
    stages{
        stage("Build"){
            steps{
                echo "Building ..."
            }
            post{
                always{
                    mail to: "geetanjali.h02@gmail.com",
                    subject: "Build Status Email",
                    body: "Build log attached!"
                }
            }
        }
        stage("Test"){
            steps{
                echo "Testing ..."
            }
        }
        stage('Code Quality Check') {
            steps {
                echo 'Checking the quality of the code'
            }
        }
        stage("Deploy"){
            steps{
                echo "Deploying ..."
            }
        }
         stage('Approval') {
            steps {
                echo 'Waiting for manual approval...'
                sleep 10
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying the code to ${PRODUCTION_ENVIRONMENT} production environment"
            }
        }
        stage("Complete"){
            steps{
                echo "Completed."
            }
        }
    }
}
