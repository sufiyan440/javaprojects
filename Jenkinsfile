pipeline {
    agent any

    stages {
        stage('Git checkout') {
            steps {
                git credentialsId: 'Gitcrd', url: 'https://github.com/sufiyan440/javaprojects.git'
            }
        }
    }
}
