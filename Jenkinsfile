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
                    def res = "${currentBuild.result}"
                    echo res
                    def id = "${currentBuild.id}"
                    echo id
                    filecontents = readFile 'sample.html'
                    echo filecontents
                    def ht = ${filecontents.('h2').innerHTML}
                    echo ht
                    emailext subject: "Hello - Testing",
                        mimeType: 'text/html',
                        body: filecontents,
                        to: "teddy86working@gmail.com"
                }
            }
        }
}
