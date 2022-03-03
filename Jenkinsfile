pipeline {
  environment {
       ACCESSTYPE_API_KEY = credentials('proenv_id')
    }
  agent any
  stages {
   stage('PROENV IDS') {
      steps{
        echo "Global property file: ${ACCESSTYPE_API_KEY}"
      }
    }
  }
}
