pipeline {
  agent any
  tools {
    maven 'Maven'
  }
  stages {
    stage('test') {
      steps {
        sh 'mvn clean test'
        echo 'testing initiated'
      }
    }
    stage('build') {
      steps {
        echo 'build initialized'
        sh 'mvn package'
      }
    }
    stage('deploy_prod') {
      steps {
        deploy adapters: [tomcat9(credentialsId: 'TOMCAT-DEPLOY_TEST', path: '', url: 'http://65.0.25.153:8081/')], contextPath: '/app', onFailure: false, war: '**/.*war'
        echo 'deploying to production'
      }
    }
  }
  post {
    always {
        echo 'pipeline exec - finished'
    }
    success {
        echo 'pipeline exec - successfully'
    }
    failure {
        echo 'pipeline exec - failed'
    }
  }
  
}
