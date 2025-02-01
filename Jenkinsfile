pipeline {
    agent any

    tools {
        maven 'Maven 3'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'master', url: 'https://github.com/souhail210301/mon-projet-jenkins.git'
            }
        }

        stage('Build with Maven') {
            steps {
                bat 'mvn clean install'  // Utilisez 'sh' au lieu de 'bat' sous Linux/Mac
            }
        }
    }
}
