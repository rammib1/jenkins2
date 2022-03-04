pipeline {
    agent any
    
      environment {
        imageName = "subs-swarajya"
        registry = "registry.digitalocean.com"
        registrySlug = "cms-swarajya"
        dockerImage = ''
        latest = "latest"
        NEXTPUBLIC_STRAPI_API_URL_S = credentials('proenv_id')
        NEXTPUBLIC_RAZORPAY_KEY_ID_S = credentials('proenv_id')
    }

  stages {
   stage('Building Image') {
      steps{
        script {
          dockerImage = docker.build imageName+":${env.BUILD_ID} --build-arg NEXTPUBLIC_STRAPI_API_URL=${NEXTPUBLIC_STRAPI_API_URL_S} --build-arg NEXTPUBLIC_RAZORPAY_KEY_ID=${NEXTPUBLIC_RAZORPAY_KEY_ID_S}"
        }
      }
    }
        stage("Env Variables") {
            steps {
                // sh "printenv"
                  sh "echo $NEXTPUBLIC_STRAPI_API_URL_S" 
                sh "echo $NEXTPUBLIC_RAZORPAY_KEY_ID_Sgm" 
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


