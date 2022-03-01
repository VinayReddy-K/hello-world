pipeline {
  agent any
  tools {
    maven 'maven3'
  }
  stages{
    stage('Build Stage'){
      steps{
        sh 'mvn clean package'
      }
    }
  }
}