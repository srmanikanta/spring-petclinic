pipeline {
    agent any
    stages { 
        stage('SCM') {
           steps {
            git 'https://github.com/srmanikanta/spring-petclinic.git'
            }
        }
        
       stage('MVN CLEAN') {
           steps {
            sh 'mvn clean'
           }    
        }

       stage('MVN package') {
           steps {
            sh 'mvn package' 
           }
        
       }
    }
}
