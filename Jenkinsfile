pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        parallel(
          "Build": {
            echo 'build'
            
          },
          "": {
            git(url: 'git@github.com:chrisshielssainsburys/thursday.git', branch: 'master')
            
          }
        )
      }
    }
    stage('Test') {
      steps {
        echo 'test'
      }
    }
    stage('Deploy') {
      steps {
        echo 'deploy'
      }
    }
    stage('Tea') {
      steps {
        echo 'have a cup of tea'
      }
    }
    stage('Ice Cream') {
      steps {
        echo 'Eat ice cream'
      }
    }
    stage('Beer') {
      steps {
        echo 'Drink beer'
      }
    }
  }
}