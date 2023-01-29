pipeline{

	agent any

        stages{

              stage('Quality Gate Status Check'){
                  steps{
                      script{
			      def scannerHome = tool 'SonarScanner';
			      withSonarQubeEnv('sonarserver') { 
			      
			      	bat "${scannerHome}/bin/sonar-scanner.bat -Dsonar.projectKey=develop"
                       	     	}
			      timeout(time: 1, unit: 'HOURS')
			      
                 	}
               	 }  
              }	






        }
}
