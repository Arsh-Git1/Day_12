pipeline {
    agent any

    environment {
        MAVEN_HOME = tool 'Maven - 3.9.0', type: 'maven' // Ensure this matches your Maven tool name
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from GitHub repository
                git url: 'https://github.com/Arsh-Git1/Day_12.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                // Build the project using Maven
                script {
                    withEnv(["PATH+MAVEN=${MAVEN_HOME}\\bin"]) {
                        sh 'mvn clean package'
                    }
                }
            }
        }

        stage('Archive Artifacts') {
            steps {
                // Archive the built artifacts
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
