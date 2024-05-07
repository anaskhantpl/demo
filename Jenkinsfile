pipeline {
    agent any

    stages {
        stage('Clone Repositories') {
            steps {
                // Clone the first repository (https://github.com/anaskhantpl/dev.git)
                git branch: 'main', url: 'https://github.com/anaskhantpl/dev.git'

                // Check out the second repository using the provided configuration
                checkout([
                    changelog: false,
                    poll: false,
                    scm: [$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: "https://github.com/anaskhantpl/demo.git"]]]
                ])
            }
        }

        stage('Build and Test') {
            steps {
                echo 'Building...' // Improved message clarity
            }
        }
    }
}
