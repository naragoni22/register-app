pipeline {
   agent { label 'Jenkins-Agent' }
   tools{
       jdk 'Java17'
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
	            git branch: 'main', credentialsId: 'github', url: 'https://github.com/naragoni22/register-app'
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
	 stage('SonarQube Analysis'){
            steps(){
			 script{
				 withSonarQubeEnv(credentialsId: 'jenkins-sonar-token'){
					         sh " mv sonar:sonar"
				 }
			 }
		 }
	 }
  }	
}
