pipeline {
  agent any
  stages {
    stage('compile') {
      steps {
        sh '''echo "Compiling"
pwd'''
        pwd(tmp: true)
        retry(count: 10) {
          echo 'Hello World'
        }
        
        readFile(file: 'README.md', encoding: 'UTF-8')
        fileExists 'README.md'
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
        input(message: 'Continue?', id: 'quangnd')
      }
    }
  }
  environment {
    REPO = 'github'
    USER = 'jenkins'
  }
}