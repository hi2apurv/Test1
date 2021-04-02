pipeline {
    agent any
    stages {
        stage('build docker image') {
   steps {
              sh 'sudo docker build  -t 13007/myfirst:1 .'
            }
        } 
stage('push docker image') {
   steps {
    withCredentials([string(credentialsId: '13007', variable: 'DOCKER_HUB_PWD')]) {
                sh "docker push -u 13007 -p ${DOCKER_HUB_PWD} 13007/myfirst:1"
    }
   }
        }
    }
}
