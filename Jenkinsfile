pipeline {
    agent any
     environment {
       NEXTPUBLIC_STRAPI_API_URL_S = credentials('proenv_id')
    }
    stages {
        stage("Env Variables") {
            steps {
                sh "printenv"
                  sh "echo $NEXTPUBLIC_STRAPI_API_URL_S" | base64
                withCredentials([file(credentialsId: 'proenv_id', variable: 'mySecretFile')]) {
                    // some block can be a groovy block as well and the variable will be available to the groovy script
                   
                 /*   sh '''
                         echo "This is the content of the file `cat $mySecretFile`"
                       ''' */
                }
            }
        }
    }
}


