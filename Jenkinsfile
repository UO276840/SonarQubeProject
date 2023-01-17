pipeline {
    agent any

    stages {
        stage('Build') {
            steps {  
                    bat 'mvn clean install'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sonarqube') {
                    bat 'mvn sonar:sonar'
                }
            }
        }
    }
}
