pipeline{

	agent any

        stages{

              stage('Quality Gate Status Check'){
                  steps{
                      script{
			      def scannerHome = tool 'sonarqube';
			      withSonarQubeEnv('sonarserver') { 
			      
			      	bat "${tool("sonarqube")}/bin/sonar-scanner"
                       	     	}
			      timeout(time: 1, unit: 'HOURS')
			      
                 	}
               	 }  
              }	






        }
}
