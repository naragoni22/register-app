pipeline {
    agent any
 tools{
    jdk 'java'
    maven 'LocalMaven'
     }
    stages{
      stage('clean up workspace'){
	steps{
	    cleanWs()
	     }
       }
      stage('checkout from SCM'){
	steps{
	    git branch: 'main', credentialsId: 'Github', url: 'https://github.com/naragoni22/register-app.git'
	     }
       }
      stage('Build application'){
	steps{
	    bat "mvn clean package"
	     }
       }
      stage('Test application'){
	steps{
	    bat "mvn test"
	     }
       }
	  
    }
	
}
