pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Joonhang35/hello-world-java1.git'
            }
        }
        stage('Build') {
            steps {

                        'gradle clean build'
                
            }
        }
        stage('Test') {
            steps {
                
                        'gradle test'
                  
            }
        }
        stage('Deploy') {
            steps {                
                        'java -jar build/libs/hello-world-java-V1.jar'
                 }           
        }
    
}

post {
        always {
            echo 'Cleaning up workspace'
            deleteDir() // Clean up the workspace after the build
        }
        success {
            echo 'Build succeeded!!'
            // You could add notification steps here, e.g., send an email
        }
        failure {
            echo 'Build failed!!'
            // You could add notification steps here, e.g., send an email or Slack message
        }
    }
    }


