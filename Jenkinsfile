#!groovy
 
pipeline {
  agent any
  stages {
    stage('Maven Install') {
      steps {
        sh './mvnw package'
      }
    }
    stage('Docker Build') {
      steps {
        sh 'docker build -t enepau/springpetclinic:v2 .'
      }
    }
    stage('Docker Push') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
          sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
          sh 'docker push enepau/springpetclinic:v2'
        }
      }
    }
  }
}
