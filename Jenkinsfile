pipeline {
    agent any
    stages {
       stage('Build') {
          steps {
             withMaven(maven : 'maven-3.6.1') {
	        sh 'mvn clean complile'
	           sh 'pwd; sudo chmod 777 build deploy test; ./build'
				
            }
        }
    }
        stage('deploy') {
			agent { label 'slave' }
            steps {
                echo 'Deploying to TEST environment..'
	:			sh 'sudo chmod 777 build deploy test; ./deploy'
            }
        }
        stage('test') {
			agent { label 'slave' }
            steps {
                echo 'Testing....'
				sh 'sudo chmod 777 build deploy test; ./test'
					}
				}
    }
}
