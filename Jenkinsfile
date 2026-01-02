pipeline {
    agent {
        node {
            label 'docker-agent-python'
        }
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build & Test') {
            steps {
                echo "Building and Testing..."
                sh '''
                cd simple-maven-app
                sh 'mvn clean test'
            }
        }

        stage('Package') {
            steps {
                echo "Packaging..."
                sh '''
                cd simple-maven-app
                sh 'mvn clean package'
            }
        }
    }
}
