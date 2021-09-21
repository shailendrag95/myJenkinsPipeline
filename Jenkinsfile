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

        stage('Log Test') {
          steps {
            writeFile(file: 'LogFile.txt', text: '1. Test completed \\n 2. file generated successfully')
          }
        }

      }
    }

    stage('Deployment') {
      parallel {

        when{
          branch 'master'
        } 
        
        stage('Deployment') {
          steps {
            input(message: 'Do you want to deploye', id: 'Ok')
            echo "message ${Dmessage}"
          }
        }

        stage('Artifect generation') {
          steps {
            archiveArtifacts 'LogFile.txt'
          }
        }

      }
    }

  }
  environment {
    Dmessage = 'Deployment completed for this Build'
  }
}