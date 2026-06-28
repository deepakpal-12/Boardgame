pipeline {

  agent any

  tools {

     maven 'maven3.6'
        jdk 'jdk17'
    }

    stages {

        stage('checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/deepakpal-12/Boardgame.git'
            }
        }

        stage('Build') {
            steps {
               sh 'mvn clean verify'
            }
        }
         stage('Sonar Scan') {
             steps {
        withSonarQubeEnv('SonarQube') {
            withCredentials([string(credentialsId: 'sonar-cred', variable: 'SONAR_TOKEN')]) {
                sh """
                    mvn sonar:sonar \
                      -Dsonar.projectKey=Board-game \
                      -Dsonar.host.url=http://localhost:9000 \
                      -Dsonar.login=$SONAR_TOKEN
                """
               }
           }
        }
   }

   

    }

}    
