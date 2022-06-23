pipeline {
    agent any
    environment{
    PATH = "/opt/maven3/bin:$PATH"
    }
    stages {
        stage('Git checkout') {
            steps {
                git credentialsId: 'Gitcrd', url: 'https://github.com/sufiyan440/javaprojects.git'
            }
        }
       stage('Maven Build) { 
        steps {
            sh "mvn clean package"
            }
        }
    }
}
