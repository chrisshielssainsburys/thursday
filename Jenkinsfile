pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        parallel(
          "Build": {
            echo 'build'
            
          },
          "Checkout": {
            git(url: 'https://github.com/chrisshielssainsburys/thursday.git', branch: 'master', credentialsId: '43a673b4-ffb0-49a0-9f7f-8770fd3a8011')
            
          },
          "": {
            input(message: 'Branchname', id: 'branchname')

            def userInput = input(
             id: 'userInput', message: 'Let\'s promote?', parameters: [
             [$class: 'TextParameterDefinition', defaultValue: 'uat', description: 'Environment', name: 'env'],
             [$class: 'TextParameterDefinition', defaultValue: 'uat1', description: 'Target', name: 'target']
            ])
            echo ("Env: "+userInput['env'])
            echo ("Target: "+userInput['target'])            
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
