def filecontents
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                script {
                   filecontents = readFile 'sample.html',
                    echo filecontents
                }
            }
        }
        
    }
}
