pipeline{
  agent any
  stages {
    stage('Upload to AWS'){
      steps {
        withAWS(region:'us-east-2',credentials:'aws-static') {
              sh 'echo "PWD:"'
              sh 'pwd'
              sh 'echo "Uploading content with AWS creds"'
                s3Upload(pathStyleAccessEnabled: true, path:'static/index.html', payloadSigningEnabled: true, file:'index.html', bucket:'jenkinsudacity-s3')
            }
      }
    }
  }
}
