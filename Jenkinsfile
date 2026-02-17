pipeline {
    agent any

    stages {

        stage('Connect') {
            steps {
                echo 'Jenkins successfully connected to GitHub!'
            }
        }

        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Hariharan-Laboratory/jenkins-cicd-demo.git'
            }
        }

        stage('Build Test') {
            steps {
                sh 'echo Build working...'
            }
        }
    }
}
