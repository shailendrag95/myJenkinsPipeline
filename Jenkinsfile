pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building Repo'
          }
        }

        stage('Test') {
          steps {
            echo 'test Repo'
          }
        }

      }
    }

    stage('Deployment') {
      steps {
        echo "message ${Dmessage}"
      }
    }

  }
  environment {
    Dmessage = 'Deployment completed for this Build'
  }
}