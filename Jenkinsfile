pipeline {
  environment {
       ACCESSTYPE_API_KEY_S = credentials('proenv_id')
    }
  agent any
  stages {
   stage('PROENV IDS') {
      steps{
                script {
                  sh "echo $ACCESSTYPE_API_KEY_S"
          withCredentials([file(credentialsId: 'proenv_id', variable: 'FILE')]) {
              sh "echo $FILE"
          }
        }
      }
    }
  }
}
