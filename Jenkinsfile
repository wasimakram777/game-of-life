pipeline {
    agent any
    stages {
       stage('Build') {
          steps {
             withMaven(maven : 'maven-3.6.1') {
	        sh 'mvn clean complile'			
            }
        }
    }
      
   }
}
