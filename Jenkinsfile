def filecontents
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
    post
        {
        always
            {
            script
                {
                   filecontents = readFile 'sample.html'
                    echo filecontents
                    emailext subject: "Hello - Testing",
                        mimeType: 'text/html',
                        to: "teddy86working@gmail.com"
                }
            }
        }
    }
}
