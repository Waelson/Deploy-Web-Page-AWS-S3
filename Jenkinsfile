pipeline {
    agent any
    
    environment{
        WORKSPACE_DIR = pwd()
    }      

    stages {
        stage('Lint HTML') {
            steps {
                echo 'Linting..'
                dir("$WORKSPACE_DIR/"){
                    sh 'tidy -q -e *.html'   
                }
            }
        }        
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
