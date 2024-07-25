pipeline {
    agent any
 
    environment {
        MAVEN_HOME = tool 'Maven - 3.9.0'
    }
 
    stages {
        stage('Checkout') {
            steps {
                
                git url: 'https://github.com/Arsh-Git1/Day_12.git', branch: 'main'
 
                
            }
        }
 
        stage('Build') {
            steps {
    
                sh 'mvn clean package'
                
            }
        }
 
        stage('Archive Artifacts') {
            steps {
        
                archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
            }
        }
    }
 
    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Pipeline succeeded.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
