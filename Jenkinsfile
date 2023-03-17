pipeline {
  agent any
  stages {
    stage('Checkout') {
      parallel {
        stage('Checkout') {
          steps {
            echo 'This Step will fetch the code from git.'
          }
        }

        stage('Test') {
          steps {
            echo 'This step will run the test suitcases.'
            echo 'Printing Variable ${globalVar}'
          }
        }

      }
    }

    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'This Step will build the project.'
          }
        }

        stage('SonarCube') {
          steps {
            echo 'Code scanning....'
          }
        }

      }
    }

    stage('Deploy to Artifactory') {
      steps {
        echo 'This step will deploy to code to artifactory.'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying......'
      }
    }

  }
  environment {
    globalVar = 'I am a global Variable.'
  }
}