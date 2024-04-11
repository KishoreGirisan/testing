def filecontents
pipeline {
    agent any

    stages 
    {
        stage('Build') 
        {
            steps {
                echo 'Building..'
            }
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
                    echo "${currentBuild.result}"
                    echo "${currentBuild.id}"
                    emailext subject: "Hello - Testing",
                        mimeType: 'text/html',
                        body: filecontents,
                        to: "teddy86working@gmail.com"
                }
            }
        }
}
