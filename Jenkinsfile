pipeline {
    agent { label 'docker-slave' }

    stages {
        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }
    }
}
