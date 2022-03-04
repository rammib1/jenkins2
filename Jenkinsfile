pipeline {
    agent any

    stages {
        stage("Env Variables") {
            steps {
                sh "printenv"
                
                sh "echo $NEXTPUBLIC_STRAPI_API_URL_S"
                
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


