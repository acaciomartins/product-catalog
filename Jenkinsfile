
pipeline {
    agent any

    stages {
        stage('Show Info') {
            steps {
                echo 'Branch: ' + env.GIT_BRANCH
                echo 'Author: ' + sh(returnStdout: true, script: "git --no-pager show -s --format='%an'").trim()
            }
        }

        stage('Run Java example') {
            steps {
                sh 'mvn spring-boot:run -Drun.arguments=--server.port=8085'
                sh 'mvn spring-boot:run'
            }    
        }
    }

}