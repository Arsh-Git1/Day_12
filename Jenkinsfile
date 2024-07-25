pipeline {
    agent any
 
    tools {
        maven 'Maven - 3.9.0'
    }
 
    stages {
        stage('Checkout') {
            steps {
                
                git url: 'https://github.com/Arsh-Git1/Day11_Jenkins.git', branch: 'main', credentialsId: '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'
 
                
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