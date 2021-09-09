pipeline {
  agent any
  options {
    skipDefaultCheckout(true)
  }
  stages{
    stage('clean workspace') {
      steps {
        cleanWs()
      }
    }
    stage('checkout') {
      steps {
        checkout scm
      }
    }
    stage('terraform') {
      steps {
        sh 'chmod +x terraformw'
        sh './terraformw init'
        sh 'terraform apply -auto-approve -no-color'
      }
    }
  }
/*  post {
    always {
      cleanWs()
    }
  } */
} 
