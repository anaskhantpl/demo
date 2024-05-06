pipeline {
    agent any
    
    stages {


        stage('Clone repositories') {
            steps {
                // Clone first repository
                git branch: 'main', url: 'https://github.com/anaskhantpl/dev.git'
            }
        }



        stage('Build and Test') {
            steps {
                echo 'building'
            }
        }
    }

        triggers {
        pollSCM('* * * * *') // Polls every 5 minutes
    }
}
