@Library('Jenkins_Shared_Library@master') _
properties = null
def loadProperties() {
 properties = readProperties file: 'pipeline.properties'
}

pipeline {
    agent any
 
  tools {
        nodejs 'nodejs' 
    }
    stages {
      stage('Load Properties'){
       steps{
       loadProperties()
       }
      }
    
        stage('Git Checkout') {
            steps {
            gitCheckout(
                branch: properties.branch,
                url: properties.giturl,
                credentials: properties.gitcredsid
            )
            }
        }
        stage('npm install'){
        steps{
        npmTasks( step: "install" ) 
        }
        }
    }
    }
