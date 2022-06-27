currentBuild.displayname = "onlineshopping-#"+currentBuild.number
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
            }
        }
    }
}
