pipeline{
  agent any
  stages {
    stage('Upload to AWS'){
      steps {
        pwd();
        withAWS(region:'us-east-2',credentials:'aws-static') {
              sh 'echo "Uploading content with AWS creds"'
                s3Upload(pathStyleAccessEnabled: true, path:'static/', payloadSigningEnabled: true, file:'index.html', bucket:'jenkinsudacity-s3')
            }
      }
    }
  }
}
