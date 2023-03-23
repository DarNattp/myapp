pipeline {
  environment{
    hostname = "localhost"
  }
  agent any
  tools {
    nodejs 'nodejs'
  }
  stages {
    stage('Serve application') {
      steps {
        sh "npm install express"
        sh "node myapp.js&"
     }
   }
    stage('Test access application') {
      steps {
        sh "curl ${hostname}:3000"
        sh "kill -9 \$(lsof -t -i:3000)"
      }
    }
  }
}
