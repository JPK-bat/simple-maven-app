pipeline {
    agent {
        docker {
            image 'maven:3.9.9-eclipse-temurin-17'
            args '--network jenkins'
        }
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Test') {
            steps {
                echo "Testing..."
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
        stage('Maven Build') {
            steps {
                echo "Building..."
                sh '''
                cd simple-maven-app
                sh 'mvn clean install'
            }
        }
    }
}
