pipeline {
    agent any
    stages {
      stage(‘Lint H T M L’) {
        steps {
          sh ‘tidy -q -e *.html’
        }
      }
      stage(‘Upload to AWS’) {
        steps {
          withAWS(region:'us-east-2',credentials:'aws-static') {
            s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkinsudacity-s3')
          }
        }
      }
    
    }
}

