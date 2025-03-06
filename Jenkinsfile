pipeline {
    agent any
 tools{
    java 'Java17'
    maven 'Maven3'
     }
    stages{
      stage('clean up workspace'){
	steps{
	    cleanWs()
	     }
       }
      stage('checkout from SCM'){
	steps{
	    git branch: 'main', credentialsId: 'github', url: 'https://github.com/naragoni22/register-app.git'
	     }
       }
      stage('Build application'){
	steps{
	    sh "mvn clean package"
	     }
       }
      stage('Test application'){
	steps{
	    sh "mvn test"
	     }
       }
	  
    }
	
}
