pipeline {
  agent any
  tools {
    maven 'maven' 
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat8(credentialsId: '8de63b71-6000-4932-a243-39ab958a5fde', path: '', url: 'http://ec2-13-232-62-97.ap-south-1.compute.amazonaws.com:8090/')], contextPath: 'hello-worldP', war: '**/*.war'
        }
         }
    }
  }
}
  

