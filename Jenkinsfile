pipeline{

agent any
	environment {
			scannerHome = tool 'SonarQubeScanner'
		    	} 
        stages {

              stage('Quality Gate Status Check'){
		   
		      
		      steps {
			      script{
				withSonarQubeEnv('sonarserver') {
				    bat "sonar-scanner"
				}        timeout(time: 10, unit: 'MINUTES') {
				    waitForQualityGate abortPipeline: true
				}
			      }
		    }
              }	
	}
}
