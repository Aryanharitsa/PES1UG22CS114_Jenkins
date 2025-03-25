pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'make -C main'
            }
        }

        stage('Test') {
            steps {
                sh './main/hello_exec'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Induced error: non-existent command
                sh 'this_command_does_not_exist'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}

