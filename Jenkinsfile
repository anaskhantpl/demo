pipeline {
    agent any
    
    stages {

        stage('GitCheckout') {
            steps {

                checkout \
                scm: [ $class : 'GitSCM', \
                     branches: [[name: '*/main']], \
                     extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'demo']], 
                                 [ $class: 'ScmName', name: 'dev' ]], \
                     userRemoteConfigs: [[ \
                         url: 'https://github.com/anaskhantpl/dev.git'  \
                     ]]
    
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
