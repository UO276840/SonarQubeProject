pipeline{

	agent any

        stages{

              stage('Quality Gate Status Check'){
                  steps{
                      script{
			      def scannerHome = tool name: 'sonar_scanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation';
			      withSonarQubeEnv('sonarserver') { 
			      
			      	bat "${scannerHome}/bin/sonar-scanner"
                       	     	}
			      timeout(time: 1, unit: 'HOURS')
			      
                 	}
               	 }  
              }	






        }
}
