pipeline {
    agent { label 'docker-slave' }

    environment {
        RECIPIENTS = 'jenkins.github2@gmail.com' // Add your email address here
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
            script {
                // Get the latest commit hash
                def commitHash = sh(script: "git rev-parse --short HEAD", returnStdout: true).trim()
                mail to: "${env.RECIPIENTS}",
                     subject: "Build Success: ${env.JOB_NAME} ${env.BUILD_NUMBER}",
                     body: """The build for branch ${env.BRANCH_NAME} was successful!
                              Commit ID: ${commitHash}
                              Build URL: ${env.BUILD_URL}"""
            }
        }
        failure {
            script {
                // Get the latest commit hash
                def commitHash = sh(script: "git rev-parse --short HEAD", returnStdout: true).trim()
                mail to: "${env.RECIPIENTS}",
                     subject: "Build Failure: ${env.JOB_NAME} ${env.BUILD_NUMBER}",
                     body: """The build for branch ${env.BRANCH_NAME} failed.
                              Commit ID: ${commitHash}
                              Build URL: ${env.BUILD_URL}"""
            }
        }
        unstable {
            script {
                // Get the latest commit hash
                def commitHash = sh(script: "git rev-parse --short HEAD", returnStdout: true).trim()
                mail to: "${env.RECIPIENTS}",
                     subject: "Build Unstable: ${env.JOB_NAME} ${env.BUILD_NUMBER}",
                     body: """The build for branch ${env.BRANCH_NAME} is unstable.
                              Commit ID: ${commitHash}
                              Build URL: ${env.BUILD_URL}"""
            }
        }
        always {
            echo 'This will always run, regardless of the build result.'
        }
    }
}
