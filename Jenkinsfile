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
                    sh 'docker build -t enepau/worker:latest .'
                   }
           }
         stage('Imagepush') {
            steps {
                    sh 'docker push enepau/worker:latest'
                   }
           }
       }
   }
