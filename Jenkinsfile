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
          "Input": {
            script {
              env.RELEASE_SCOPE = input message: 'User input required', ok: 'Release!',
              parameters: [
                choice(name: 'RELEASE_SCOPE',
                       choices: 'patch\nminor\nmajor',
                       description: 'What is the release scope?')
              ]
            }
          }
        )
      }
    }
    stage('Test') {
      steps {
        parallel(
          "Test": {
            echo 'test'
            
          },
          "Echo": {
            echo '${env.RELEASE_SCOPE}'
            script {
              echo "${env.RELEASE_SCOPE}"
            }
            
            
          }
        )
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
  environment {
    hello = 'there'
    hello2 = ''
  }
}
