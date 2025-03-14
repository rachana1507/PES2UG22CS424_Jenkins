pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                build 'PES2UG22CS424-1'
                sh 'g++ pes2ug22cs424.cpp -o output'
                sh 'make'
            }
        }
        stage('Test') {
            steps {
                sh './main/hello_exec'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deployment Successful'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline Failed'
        }
    }
}
