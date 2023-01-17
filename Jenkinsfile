pipeline {
    agent any

    stages {
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
