pipeline {
    agent any
    tools { 
        maven 'M2_HOME' 
        jdk 'JAVA_HOME' 
    }
    stages {
        stage ('Build') {
            steps {
                sh 'mvn clean compile'
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                
            }
        }

        stage ('Deploy') {
            sshagent(['tomcat.dev']) {
    
            steps {
               sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@13.233.46.164:/home/ec2-user/tomcat/apache-tomcat-8.5.40/webapps/'
                }
            }
        }
    }
}
