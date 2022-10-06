pipeline {
 agent any
 stages {
	stage('Checkout GIT'){
	steps {
		echo 'Pulling...';
    	sh """ mvn clean install """;
	sh """ mvn clean test """;
		}
	}
	}
}