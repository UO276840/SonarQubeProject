pipeline{

	agent any

        stages{

              stage('Quality Gate Status Check'){
                  steps{
                      script{
			      withSonarQubeEnv('sonarserver') { 
			      
			      	bat "gradle sonarqube"
                       	     	}
			      timeout(time: 1, unit: 'HOURS')
			      
                 	}
               	 }  
              }	






        }
}
