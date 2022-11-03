pipeline {
 agent any
 stages {
	stage('Checkout GIT'){
	environment 	{
        	EMAIL_TO = 'cyrine.louati@esprit.tn'
    			}
	steps {
		echo 'Pulling from GIT...';
    		sh """ mvn --version """;
		sh """ mvn clean """;
		sh """ mvn install """;
		sh """ mvn clean test """;
		}
	post 	{
 		failure {
  		emailext body: 'Build FAILED', 
                    to: "${EMAIL_TO}", 
                    subject: 'Build failed in Jenkins: $PROJECT_NAME'
        
 			} 
		}
	
	}
	stage('Docker'){
	steps {
		echo 'Constructing/Pulling Docker image...';
    		sh """  docker build -t cyrinelo/* """;
		sh """ docker pull * """;
		}
	
	}


	}
}