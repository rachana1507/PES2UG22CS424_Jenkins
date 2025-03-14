pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/rachana1507/PES2UG22CS424_Jenkins.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                echo 'Building the C++ code'
                sh 'g++ main/helo2.cpp -o main/output'  // Ensure the file name is correct
            }
        }

        stage('Test') {
            steps {
                echo 'Running compiled program'
                sh './main/output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
