pipeline {
    agent any  

    tools {
        maven 'maven'  
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/PSS004/1bi22cs132.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'  
            }
        }

        
        
       
        stage('Run Application') {
            steps {
                
                sh 'java -jar target/1bi22cs132-1.0-SNAPSHOT.jar'

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
