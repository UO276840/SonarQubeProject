pipeline{

agent any
	
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
