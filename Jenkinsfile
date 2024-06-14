pipeline {
    agent any
    tools {
        maven 'maven'
    }
    environment {
        SONARQUBE_CREDS = credentials('sss') 
        }
    options {
        
        // Keep only the last 2 builds
        buildDiscarder(logRotator(numToKeepStr: '2'))
    }

  
    stages {
        stage('Git Checkout') {
            steps {
                git 'https://github.com/sresrinivas/testrepo.git'
                
            }
        }
        stage('clean'){
            steps{
                sh 'mvn clean'
            }
        }
        stage('compile'){
            steps{
            sh 'mvn compile'
        }
        }
        stage('test'){
            steps{
                sh 'mvn test'
            }
        }
        
         } 

}
