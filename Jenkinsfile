pipeline {
 agent any
 stages {
	stage('Checkout GIT'){
	environment {
        	EMAIL_TO = 'cyrine.louati@esprit.tn'
    	}
	steps {
		echo 'Pulling...';
    		sh """ mvn --version """;
		sh """ mvn clean install """;
		sh """ mvn clean test """;
		}
	post {
 		failure {
  		emailext body: 'Build FAILED', 
                    to: "${EMAIL_TO}", 
                    subject: 'Build failed in Jenkins: $PROJECT_NAME'
        
 		} 
	}
	}
}
}