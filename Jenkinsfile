pipeline {
    agent any
    tools {
        gradle 'Gradle'  // Use globally configured Gradle in Jenkins
        jdk 'JDK'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Divyanshu03chauhan103/GradleJenkins.git'
            }
        }
        stage('Build') {
            steps {
                sh 'gradle clean build'  // Use globally configured Gradle
            }
        }
        stage('Test') {
            steps {
                sh 'gradle test'  // Run tests
            }
        }
        stage('Run Application') {
            steps {
                sh 'gradle run'  // Run the application
            }
        }
    }
    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}

