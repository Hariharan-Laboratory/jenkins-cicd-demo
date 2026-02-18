pipeline {
    agent any

    tools {
        maven 'maven'
    }

    stages {

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
                        url: 'http://host.docker.internal:9090'
                    )
                ],
                contextPath: 'cicd-demo',
                war: '**/*.war'
            }
        }
    }
}
