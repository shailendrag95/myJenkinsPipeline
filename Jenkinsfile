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
        echo 'Deoploying'
      }
    }

  }
}