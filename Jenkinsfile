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
                    writeFile encoding: 'utf8', file: 'sample.html', text: '''res=${currentbuild.status}
                    id=${currentbuild.id}'''
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
