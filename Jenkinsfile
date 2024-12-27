pipeline {
    agent { label 'docker-slave' }

    stages {
        stage('Testing') {
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
