pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('pull scm git') {
            steps {
                git branch: 'multiple_serever_deploy',
                    credentialsId: '980dded3-7c5c-4354-a25b-7121c92ca0a4',
                    url: 'https://github.com/Arun106/Amazon-Jenkins.git'
            }
        }

        stage('compile') {
            steps {
                bat 'mvn compile'
            }
        }

        stage('build') {
            steps {
                bat 'mvn clean install'
            }
        }

        stage('deploy to tomcat 8081') {
            steps {
                deploy adapters: [
                    tomcat9(
                        credentialsId: 'tomcat-credentials',
                        path: '',
                        url: 'http://localhost:8081'
                    )
                ],
                contextPath: 'myapp',
                war: '**/*.war'
            }
        }

        stage('deploy to tomcat 8082') {
            steps {
                deploy adapters: [
                    tomcat9(
                        credentialsId: 'tomcat-credentials',
                        path: '',
                        url: 'http://localhost:8082'
                    )
                ],
                contextPath: 'myapp',
                war: '**/*.war'
            }
        }

        stage('deploy to tomcat 8083') {
            steps {
                deploy adapters: [
                    tomcat9(
                        credentialsId: 'tomcat-credentials',
                        path: '',
                        url: 'http://localhost:8083'
                    )
                ],
                contextPath: 'myapp',
                war: '**/*.war'
            }
        }

        stage('deploy to tomcat 8084') {
            steps {
                deploy adapters: [
                    tomcat9(
                        credentialsId: 'tomcat-credentials',
                        path: '',
                        url: 'http://localhost:8084'
                    )
                ],
                contextPath: 'myapp',
                war: '**/*.war'
            }
        }

    }

    post {
        success {
            echo 'Deployed to all 4 Tomcats successfully!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
