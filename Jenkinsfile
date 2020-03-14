pipeline {
    agent any

    stages {
        stage('Upload to AWS') {
            steps {
                echo 'Uploading files to S3...'
                withAWS(region:'us-west-2',credentials:'aws-static') {
                    s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'waelson-static-web-site')
                 } 
            }
        }
    }
}
