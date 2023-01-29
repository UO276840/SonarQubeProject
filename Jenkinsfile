pipeline{

	agent any

        stages{

              stage('Quality Gate Status Check'){
                  steps{
                      script{
			      def scannerHome = tool 'SonarScanner 4.8';
			      withSonarQubeEnv('sonarserver') { 
			      
			      	bat "${scannerHome}/bin/sonar-scanner"
                       	     	}
			      timeout(time: 1, unit: 'HOURS')
			      
                 	}
               	 }  
              }	






        }
}
