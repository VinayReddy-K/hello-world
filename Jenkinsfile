pipeline{
  agent any
  tools {
    maven 'maven3'
  }
  stages{
//stage('SCM Checkout'){
//  steps{
//    git url: 'https://github.com/VinayReddy-K/hello-world.git', branch: 'main'
//  }
//}
    stage('Bulid stage'){
      steps{
        sh '''
          mvn clean package
          cp /var/lib/jenkins/workspace/jenkins-docker/webapp/target/webapp.war .
        '''  
      }
    }
//    stage('Deploying War file'){
//      steps{
//        sshagent(['tomcat_server']) {
//          sh '''
//            scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/Hello/webapp/target/webapp.war ec2-user@172.31.91.151:/opt/apache-tomcat-9.0.58/webapps
//          '''
//        }
//      }
//    }
//    stage('Build Docker Image'){
//      steps{
//        sh 'docker build . -t secondimg'
//      }
//    }
  }
}