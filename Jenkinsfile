pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                branches: [[name: '*/main']], 
                userRemoteConfigs: [[url: 'https://github.com/Mohith344/PES1UG22CS359_Jenkins.git']]])
            }
        }
        stage('Build') {
            steps {
                sh 'g++ -o PES1UG22CS359-1 main.cpp' // Compiles C++ file
            }
        }
        stage('Test') {
            steps {
                sh './PES1UG22CS359-1' // Runs the compiled file
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying the application..."
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed' // Post action in case of failure
        }
    }
}
