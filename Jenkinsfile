pipeline {
    agent any

    tools {
        maven 'Maven 3' // Ensure this name matches what's configured in Jenkins Global Tools Configuration
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'master', url: 'https://github.com/mhassini/avec-maven.git'
            }
        }
        stage('Build with Maven') {
            steps {
                script {
                    // Using the Maven tool specified in the tools section
                    def mvnHome = tool 'Maven 3'
                    if (isUnix()) {
                        sh "${mvnHome}/bin/mvn clean install"
                    } else {
                        bat "\"${mvnHome}\\bin\\mvn\" clean install"
                    }
                }
            }
        }
    }

    post {
        always {
            // Archive artifacts or perform other cleanup actions here
            echo 'Pipeline completed.'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
