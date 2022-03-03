pipeline {
  environment {
       PROENV_IDS = credentials('proenv_id')
    }
  agent any
  stages {
   stage('PROENV IDS') {
      steps{
        echo "Global property file: ${PROENV_IDS}"
      }
    }
  }
}
