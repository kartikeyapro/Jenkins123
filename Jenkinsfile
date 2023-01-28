pipeline {
    agent any
	tools {
		maven 'maven'
       
    }

    stages {
        stage('Code Clone') {
            steps {
			   git credentialsId: 'github', url: 'https://github.com/kartikeyapro/ks.git'                          
            }
			}

		stage('Code Clean') {
            steps {
             sh 'mvn clean' 
                
            }
           
            }
        stage('Code Validate') {
            steps {
              sh 'mvn validate'
                
            }
			}

		stage('Code Compile') {
            steps {
             sh 'mvn compile' 
                
            }
           }
       stage('Code Test') {
            steps {
              sh 'mvn test'
                
            }
			}
	   stage('Code Test') {
            steps {		
		      sh 'mvn sonar:sonar -Dsonar.host.url=http://34.68.133.210:9000 -Dsonar.login=32aa7ed3793424ab043cd6e6fa227ab9781c5c97'	
			  }
			  }

		stage('Code Package') {
            steps {
             sh 'mvn package' 
                
            }
           }		
	    stage('Code Deploy') {
            steps {
             sh 'mvn deploy' 
                
            }
           }			   		
}
}
