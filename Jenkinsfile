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
                    def ht = document.getElementById("h2");
                    echo ht
                    writeFile file: 'sample.html', text: '''res : ${currentBuild.result}
                    id : "${currentBuild.id}"'''
                    filecontents = readFile 'sample.html'
                    echo filecontents
                    emailext subject: "Hello - Testing",
                        mimeType: 'text/html',
                        body: filecontents,
                        to: "teddy86working@gmail.com"
                }
            }
        }
}
