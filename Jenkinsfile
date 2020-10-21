
@Library("sonar@master") _

def readProp; 

pipeline {
    agent any 
    stages {
      stage('test the properties') {
      steps {
	    script {
	    try {        
        readProp = readProperties file: "pipeline.properties"
	      echo """The branch name is ${readProp['branch']}"""
	      echo """The repo name is ${readProp['url']}"""
	      echo "The cred id is ${readProp['credId']} "
            }
      catch(Exception e) {
	      echo e.getMessage()
	      echo "The test properties stage have some errors"
	          }
	        }
	      }
	    }
      stage('checkout git') {
      steps {
      gitCheckout(
        branch: "${readProp['branch']}", 
        repourl: "${readProp['url']}",
	credId: "${readProp['credId']}"
	    )
        }
      }
      /*
      stage('maven package') {
      steps {
        sh 'mvn clean package'
        }
      }

      stage('SonarQube analysis') {
      steps { 
        withSonarQubeEnv('sonarqube') { 
          sh 'mvn sonar:sonar'
  	      }
	      }
      }
      stage('quality gates') {
      steps { 
        sonarAnalysis()
        }
      }
      */
    }

  } 
