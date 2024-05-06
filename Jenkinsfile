pipeline {
    agent any
    
    stages {

        stage('GitCheckout') {
            steps {
                script {
                    checkout scm: [
                        $class: 'GitSCM',
                        branches: [[name: 'main']],
                        userRemoteConfigs: [[url: 'https://github.com/anaskhantpl/dev.git']]
                    ]
                }
            }
        }

        stage('Build and Test') {
            steps {
                echo 'building'
            }
        }
    }
}
