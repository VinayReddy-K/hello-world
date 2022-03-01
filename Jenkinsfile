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
        sh 'mvn clean package'
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
    stage('Bulid Docker image')
      steps{
        sh 'docker build -t secondimg .'
      }
    }
    stage('Push Docker image')
      steps{
        withCredentials([string(credentialsId: 'dockerhubpwd', variable: 'dockerhubpwd')]) {
          sh "docker login -u kachana -p $(dockerhubpwd)"
          sh "docker push kachana/secondimg"
        }
      }
    }
  }
}