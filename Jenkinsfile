pipeline {
    agent any
     stages {
        stage('MavenPackage') {
            steps {
                sh './mvnw package'
             }
        }
         stage('DockerBuild') {
            steps {
                    sh 'docker build -t enepau/spring-petclinic:latest'
                   }
           }
         stage('Imagepush') {
            steps {
                    sh 'docker push enepau/spring-petclinic:latest'
                   }
           }
       }
   }
