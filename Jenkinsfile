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
                    sh 'mvn sonar:sonar'
                }
            }
        }
   

    }

}    
