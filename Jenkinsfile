currentBuild.displayName = "onlineshopping-#"+currentBuild.number

pipeline {
    agent any
    environment {
    PATH = "/usr/share/maven/bin:$PATH"
    }
    stages {
        stage('Git checkout') {
            steps {
                git credentialsId: 'Gitcrd', url: 'https://github.com/sufiyan440/javaprojects.git'
            }
        }
       stage('Maven Build') { 
        steps {
            sh "mvn clean package"
            sh"mv target/*.jar target/myweb.jar"
            }
        }
        stage('deploy-dev'){
            steps {
        sshagent(['tomcat']) {
           sh""""
           scp -o StrictHostKeyChecking=no target/myweb.jar ubuntu@172.31.11.128:/tomcat8/webapps/
           ssh ubuntu@172.31.11.128 /opt/tomcat8/bin/shutdown.sh
           ssh ubuntu@172.31.11.128 /opt/tomcat8/bin/startup.sh
           
           """
                 }
            }
        }             
    }
}
