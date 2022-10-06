pipeline {
 agent any
 stages {
	stage('Checkout GIT'){
	steps {
		echo 'Pulling...';
    		git branch:'master',
    		url : 'https://github.com/CyrineLouati/Atelier_DevOps.git',
    	sh """mvn clean install""";
		}
	}
	}
}