pipeline {
  agent any
  tools {
    maven 'maven3'
  }
  stages{
    stage('Build Stage'){
      sh 'mvn clean package'
    }
  }
}