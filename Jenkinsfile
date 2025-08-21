pipeline {
    agent any
    tools {
        maven 'maven 3.9.11'
        jdk   'jdk11'
    }
    stages {
        stage('Git') {
            steps {
                git branch: 'main', url: 'https://github.com/jaiswaladi246/Boardgame.git'
            }
        }
       stage('Compile'){
            steps {
                sh 'mvn compile'
            }
       }
       stage('Package'){
           steps {
               sh 'mvn package'
           }
       }    
             

        }
    }
  
