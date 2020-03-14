pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Hello world!!'
                sh '''
                  echo "Multiline shell steps works too"
                  ls -lah
                '''
            }
        }
    }
}
