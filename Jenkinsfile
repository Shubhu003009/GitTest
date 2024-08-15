pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''pwd
ls
mkdir test
ls
date'''
        echo 'added test folder'
      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            sh '''pwd
ls
cd test
touch test.txt
ls
cd ..
ls'''
            echo 'added text.txt to test dir'
          }
        }

        stage('   test parallel') {
          steps {
            sh 'whoami'
            echo 'logged in user'
          }
        }

      }
    }

    stage('deploy') {
      steps {
        sh '''pwd
ls
whoami
hostname -i'''
        echo 'deployed to production'
      }
    }

  }
}