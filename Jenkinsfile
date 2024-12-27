pipeline {
    agent { label 'docker-slave' }

    environment {
        RECIPIENTS = 'youremail@example.com' // Add your email address here
    }

    stages {
        stage('Test') {
            steps {
                echo "Running tests for branch ${env.BRANCH_NAME}..."
                // Simulate a failure for testing purposes
                // sh 'exit 1' // Uncomment this to simulate failure
            }
        }

        stage('Build') {
            steps {
                echo "Building the project for branch ${env.BRANCH_NAME}..."
            }
        }
    }

    post {
        success {
            mail to: "${env.RECIPIENTS}",
                 subject: "Build Success: ${env.JOB_NAME} ${env.BUILD_NUMBER}",
                 body: "The build for branch ${env.BRANCH_NAME} was successful!\n\n" +
                       "Build URL: ${env.BUILD_URL}"
        }
        failure {
            mail to: "${env.RECIPIENTS}",
                 subject: "Build Failure: ${env.JOB_NAME} ${env.BUILD_NUMBER}",
                 body: "The build for branch ${env.BRANCH_NAME} failed.\n\n" +
                       "Build URL: ${env.BUILD_URL}"
        }
        unstable {
            mail to: "${env.RECIPIENTS}",
                 subject: "Build Unstable: ${env.JOB_NAME} ${env.BUILD_NUMBER}",
                 body: "The build for branch ${env.BRANCH_NAME} is unstable.\n\n" +
                       "Build URL: ${env.BUILD_URL}"
        }
        always {
            echo 'This will always run, regardless of the build result.'
        }
    }
}
