pipeline {
  environment {
       ACCESSTYPE_API_KEY_S = credentials('proenv_id')
    }
  agent any
  stages {
   stage('PROENV IDS') {
      steps{
                script {
          withCredentials([file(credentialsId: 'proenv_id', variable: 'FILE')]) {
               sh "echo $FILE" | base64
          }
        }
      }
    }
  }
}
