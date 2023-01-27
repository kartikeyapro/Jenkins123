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
