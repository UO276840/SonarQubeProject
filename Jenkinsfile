pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/UO276840/SonarQubeProject.git'
            }
        }

        stage('Build') {
            steps {
                withMaven(maven: 'maven:latest') {
                    sh 'mvn clean install'
                }
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sonarqube') {
                    sh 'mvn sonar:sonar'
                }
            }
        }
    }
}
