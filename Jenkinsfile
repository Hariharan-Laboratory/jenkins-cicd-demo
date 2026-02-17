pipeline {
    agent any

    tools {
        maven 'maven'
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/Hariharan-Laboratory/jenkins-cicd-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [
                    tomcat9(
                        credentialsId: 'tomcat-user',
                        path: '',
                        url: 'http://host.docker.internal:9090'
                    )
                ],
                contextPath: 'cicd-demo',
                war: '**/*.war'
            }
        }
    }
}
