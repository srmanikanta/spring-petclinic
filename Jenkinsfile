@Library('sonar@main') _
pipeline {
    agent any
    stages { 
        stage('git checkout') {
           steps {
           checkoutSource(
            branch: "master",
            url: "https://github.com/srmanikanta/spring-petclinic.git"
            credentialid: "mycredential-1"   
           ) 
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
