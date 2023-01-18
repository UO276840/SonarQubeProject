pipeline{

agent any
	
        stages {

              stage('Quality Gate Status Check'){
		      environment {
			scannerHome = tool 'SonarQubeScanner'
		    	} 
		      
		      steps {
			withSonarQubeEnv('sonarserver') {
			    bat "${scannerHome}/bin/sonar-scanner"
			}        timeout(time: 10, unit: 'MINUTES') {
			    waitForQualityGate abortPipeline: true
			}
		    }
              }	
	}
}
