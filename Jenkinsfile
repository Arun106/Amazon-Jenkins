pipeline {
    agent any

    tools {
        maven 'Maven'    // tells Jenkins to use Maven from Manage Jenkins → Tools
    }

    stages {

        stage('pull scm git') {
            steps {
                git branch: 'Demo_branch_windows',
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

    }

    post {
        success {
            echo 'Build success!'
        }
        failure {
            echo 'Failure in the build'
        }
    }
}
