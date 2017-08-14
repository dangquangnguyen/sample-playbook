pipeline {
  agent any
  stages {
    stage('compile') {
      steps {
        sh '''echo "Compiling"
pwd'''
      }
    }
    stage('testing') {
      steps {
        echo 'Testing'
      }
    }
    stage('baking') {
      steps {
        echo 'Baking AMI'
      }
    }
    stage('staging') {
      steps {
        echo 'Deploy to Staging'
      }
    }
    stage('prod promotion') {
      steps {
        echo 'prod promotion'
      }
    }
  }
  environment {
    REPO = 'github'
    USER = 'jenkins'
  }
}