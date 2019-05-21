pipeline {
  agent any
  stages {
    stage('Say Hello') {
      steps {
        echo 'Hello World!'   
        sh 'java -version'
      }
    }
  


    stage('Test') {
     agent { label 'nodejs-app' }
      options { 
          buildDiscarder(logRotator(numToKeepStr: '2'))
          skipDefaultCheckout true
        }
     steps {
        sh 'java -version'
         checkout scm

        container('nodejs') {
          echo 'Hello World!'   
          sh 'node --version'
        }
      }
    }
  }
}

