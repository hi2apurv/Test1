pipeline {
    environment{
        registry="13007/myfirst"
        registryCredential="13007"
        dockerImage=""
    }
    
        agent any
    stages {
        stage('build docker image') {
   steps {
       script{
           dockerImage = docker.build registry + ":$BUILD_NUMBER"
       }
            }
        } 
stage('push docker image') {
   steps {
       script{
           docker.withRegistry('https://registry.hub.docker.com', registryCredential){
               dockerImage.push()
           }
   }
        }
    }
}
}
