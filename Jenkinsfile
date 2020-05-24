pipeline {
     agent any
     stages {
        //  stage('Build') {
        //      steps {
        //          sh 'echo "Hello World"'
        //          sh '''
        //              echo "Multiline shell steps works too"
        //              ls -lah
        //          '''
        //      }
        //  }
         stage('Upload to AWS') {
             steps {
                withAWS(region:'us-east-2', credentials:'aws-static') {
                    // do something
                    sh 'echo Uploading Files to AWS'
                    s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkinsproject')
                    sh 'echo Uploading Files to AWS Completed'
                }
             }
         }
	}
}