pipeline {
  agent any
  stages {
    stage('verify installations') {
      steps {
       
        bat  "php -v"
         bat "phpunit --version"
      
      }
    }
    stage('run tests') {
      steps {
        bat "phpunit --bootstrap src\\autoload.php tests"
      }
    }
    stage ('run tests with TestDox') {
      steps {
        bat "phpunit --bootstrap src\\autoload.php --testdox tests"
      }
    }
    stage ('run tests with JUnit results') {
      steps {
        bat "phpunit --bootstrap src\\autoload.php --log-junit target\\junit-results.xml tests"
      }
      post {
        always {
          junit testResults: 'target\\*.xml'
        }
      }
    }
  }
}
