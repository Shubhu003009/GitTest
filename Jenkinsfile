pipeline {
  agent any
  stages {
    stage('test') {
      agent any
      steps {
        tool(name: 'Maven', type: 'testing-tool')
        sh 'mvn clean test'
        echo 'testing initiated'
      }
    }

    stage('build') {
      agent any
      steps {
        tool(name: 'Maven', type: 'testing-tool')
        echo 'build initialized'
        sh 'mvn clean install'
      }
    }

    stage('deploy_test') {
      agent any
      steps {
        sh '''pwd
ls
whoami
hostname -i'''
        echo 'deployed to production'
      }
    }

    stage('deploy_prod') {
      agent any
      steps {
        echo 'deploying to production'
      }
    }

  }
}