pipeline {
    agent {
        docker {
            image 'maven:3.6.3-jdk-11'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/ejemplo/repo.git'
            }
        }
        stage('Build and SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh 'mvn clean install sonar:sonar'
                }
            }
        }
    }
}
