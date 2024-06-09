pipeline {
  agent any
  stages {
    stage('verify installations') {
      steps {
       
        bat  "php -v"
        bat "​composer require --dev phpunit/phpunit"
        bat ".\\vendor\\bin\\phpunit --version"
        bat "composer dump-autload"
        
      }
    }
    stage('run tests') {
      steps {
        bat ".\\vendor\\bin\\phpunit"
      }
    }
  

  }
}
