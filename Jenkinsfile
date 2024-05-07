pipeline {
    agent any

    triggers {
        scm([
            $class: 'GitSCM', 
            branches: [[name: '*/main']], 
            extensions: [[$class: 'PollSCMChanges']], 
            repositories: [[url: 'https://github.com/anaskhantpl/dev.git']]
        ])
    }

    stages {
        stage('Clone Repositories') {
            steps {
                // Clone the first repository (https://github.com/anaskhantpl/dev.git)
                git branch: 'main', url: 'https://github.com/anaskhantpl/dev.git'

                // Checkout the second repository using the provided configuration (no polling)
                checkout([
                    changelog: false,
                    poll: false, // Explicitly disable polling
                    scm: [$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/anaskhantpl/demo.git']]]
                )
            }
        }

        stage('Build and Test') {
            steps {
                echo 'Building...'
            }
        }
    }
}
