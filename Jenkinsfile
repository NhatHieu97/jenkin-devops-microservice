//SCRIPTED

//DECLARATIVE
pipeline {
    agent any
    stages {
	stage('Build') {
	   steps {
	        withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') 
	        {
    		     sh 'docker build -t nhathieu97/nodejs-test:v10 .'
    		     sh 'docker push -t nhathieu97/nodejs-test:v10 .'
    		}
	   }
	}
	stage('Test') {
	   steps {
		echo "Test"
	   }
	}
	stage('Integration Test') {
	   steps {
		echo "Integration Test"
	   }
	}
    }	
    post {
	always {
	    echo 'Im awesome. I run always'
	}
	success {
	    echo 'Im run when you are successful'
	}
	failure {
	    echo 'Im run when you are failure'
	}			
    }	
}
