pipeline {
  agent any
  options { 
      buildDiscarder(logRotator(numToKeepStr: '2'))
      skipDefaultCheckout true
    }
  stages {
    stage('Say Hello') {
      steps {
        echo 'Hello World!'   
        sh 'java -version'
      }
    }
  
    stage('Test') {
     agent { label 'nodejs-app' }
      
     steps {
        sh 'java -version'
         checkout scm

        container('nodejs') {
          echo 'Hello World!'   
          sh 'node --version'
        }
      }
    }
    stage('Build and Push Image') {
      when {
         beforeAgent true
         branch 'master'
      }
      steps {
         echo "TODO - build and push image"
      }
    }
    
  }
}
