
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
        
        stage('Deploy') {
            steps {
                script {
                    deploy adapters: [tomcat9(credentialsId: 'a9d31f57-54ec-4f6c-96bf-df4e6bd48844', path: '', url: 'http://3.144.38.160:8080')], null, war: '**/*.war'
            }
        }
    }
    
        
