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
            steps {
               sh 'cp -o StrictHostKeyChecking=no target/*.war /home/ec2-user/tomcat/apache-tomcat-8.5.40/webapps/'
            }
        }
    }
}
