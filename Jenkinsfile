pipeline {

  agent any
  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', 
        url: 'git@github.com:Jiwon-sim/source-maven-java-spring-hello-webapp.git'
      }
    }
    stage('Build') {
      steps {
        sh '<MAVEN_BUILD_COMMAND>'
      }
    }
    stage('Test') {
      steps {
        sh '<MAVEN_TEST_COMMAND>'
      }
    }
    stage('Deploy') {
      steps {
        deploy adapters: [tomcat9(credentialsId: 'tomcat-manager', url: 'http://192.168.56.102:8080')], contextPath: null, war: 'taret/hello-world.war'
      }
    }
  }
}
