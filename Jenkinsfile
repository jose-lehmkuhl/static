pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'tidy -q -e *.html'
                withAWS(credentials:'aws-static') { 
                    s3Upload(file:'index.html', bucket:'joseudacityproject3', path:'')
                }
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}