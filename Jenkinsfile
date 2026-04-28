pipeline {
    agent any
    environment {
        // Use PATH+EXTRA to append to PATH properly
        PATH = "/usr/bin:/bin:/opt/homebrew/bin"
    }
    stages {

        stage('pull scm git ') {
            steps {
                git branch: 'Demo_branch_windows', url: 'https://github.com/Arun106/Amazon-Jenkins.git'
            }
        }
        stage('compile ') {
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

  post{

  success{
     echo 'Build success 1'
  }
    
  failure{
       echo 'Failure in the build'
   }

  }


}
